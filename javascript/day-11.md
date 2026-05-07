# Day 11 — API + UI

> **Goal:** Fetch API data and display it in the DOM with loading and error states.

---

## Short Explanation

Logging API data is useful, but real users need to see data on the page. A good frontend shows what is happening: loading while waiting, content when data arrives, and an error if something fails. This pattern is used in React and most frontend frameworks too. Keep the UI simple today. Select a container, set loading text, fetch data, clear the container, then render cards or list items. If the request fails, show a friendly error message.

---

## Code Examples

`index.html`:

```html
<h1>Users</h1>
<div id="status"></div>
<div id="users"></div>
<script src="script.js"></script>
```

`script.js`:

```js
const statusMessage = document.querySelector("#status");
const usersContainer = document.querySelector("#users");

function renderUser(user) {
  const card = document.createElement("div");
  card.classList.add("user-card");

  card.innerHTML = `
    <h2>${user.name}</h2>
    <p>${user.email}</p>
    <p>${user.company.name}</p>
  `;

  usersContainer.appendChild(card);
}

async function loadUsers() {
  try {
    statusMessage.textContent = "Loading users...";

    const response = await fetch("https://jsonplaceholder.typicode.com/users");

    if (!response.ok) {
      throw new Error("Could not load users");
    }

    const users = await response.json();

    statusMessage.textContent = "";
    usersContainer.innerHTML = "";

    users.forEach((user) => {
      renderUser(user);
    });
  } catch (error) {
    statusMessage.textContent = "Unable to load users. Please try again later.";
  }
}

loadUsers();
```

---

## Exercises

1. Render API user data into cards or list items.
2. Show `"Loading..."` before the request finishes.
3. Show a useful error message if the request fails.

---

## Mini-Project

Fetch users or posts and display them in the UI.

Requirements:

- Use separate `status` and `content` elements
- Show a loading message
- Render at least five API records
- Use `createElement` or `innerHTML` intentionally
- Show an error message in the UI if the API fails

---

## Expected Outcome

You can turn API data into visible UI and handle the basic states real frontend apps need.
---

## Navigation

[← Day 10](day-10) | [Day 12 →](day-12)
