# Day 12 — Clean Code + Structure

> **Goal:** Organize a frontend project into separate files and split data logic from UI logic.

---

## Short Explanation

Small examples can live in one file, but real projects need structure. Keep HTML for structure, CSS for styling, and JavaScript for behavior. In JavaScript, separate the code that fetches data from the code that renders data. Clear function names make your project easier to debug. Avoid giant blocks of code inside one event listener. This is also how React will feel later: data changes, then UI renders from that data. Today you will refactor yesterday's API project into a cleaner shape.

---

## Code Examples

Project structure:

```text
api-users-project/
├── index.html
├── style.css
└── script.js
```

`index.html`:

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>API Users</title>
  <link rel="stylesheet" href="style.css">
</head>
<body>
  <main>
    <h1>API Users</h1>
    <p id="status"></p>
    <section id="users"></section>
  </main>

  <script src="script.js"></script>
</body>
</html>
```

`script.js`:

```js
const statusMessage = document.querySelector("#status");
const usersContainer = document.querySelector("#users");

async function fetchUsers() {
  const response = await fetch("https://jsonplaceholder.typicode.com/users");

  if (!response.ok) {
    throw new Error("Failed to fetch users");
  }

  return response.json();
}

function renderUsers(users) {
  usersContainer.innerHTML = "";

  users.forEach((user) => {
    const card = document.createElement("article");
    card.classList.add("user-card");
    card.innerHTML = `<h2>${user.name}</h2><p>${user.email}</p>`;
    usersContainer.appendChild(card);
  });
}

async function init() {
  try {
    statusMessage.textContent = "Loading...";
    const users = await fetchUsers();
    statusMessage.textContent = "";
    renderUsers(users);
  } catch (error) {
    statusMessage.textContent = "Could not load users.";
  }
}

init();
```

---

## Exercises

1. Move inline JavaScript from an HTML file into `script.js`.
2. Rename unclear variables like `data` or `x` to names that explain their purpose.
3. Split API loading and UI rendering into separate functions.

---

## Mini-Task

Refactor yesterday's API project into this structure:

```text
index.html
style.css
script.js
```

Requirements:

- `index.html` has no inline JavaScript
- `style.css` contains all styling
- `script.js` contains clear functions
- One function fetches data
- One function renders data
- One function starts the app

---

## Expected Outcome

You can organize a small frontend project so another developer can understand, run, and improve it.

---

## Navigation

[← Day 11](day-11) | [Day 13–14 →](day-13-14)
