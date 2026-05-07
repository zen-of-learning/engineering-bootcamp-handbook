# Day 12 — Clean Code and Project Structure

## Goal

Students should learn how to organize frontend code in a clean, beginner-friendly way.

---

## Practical Explanation

As projects grow, messy code becomes hard to fix.

Bad code usually has:

- Everything in one giant function
- Repeated code
- Unclear variable names
- No separation between fetching and rendering
- No structure

Clean frontend code separates responsibilities.

For example:

```text
fetchUsers    → gets data
renderUsers   → displays data
showLoading   → shows loading message
showError     → shows error message
setupEvents   → connects event listeners
init          → starts the app
```

---

## File Structure

```text
project/
  index.html
  style.css
  script.js
```

---

## Basic HTML

```html
<h1>User Directory</h1>
<p id="status"></p>
<div id="users"></div>
```

---

## Messy Version

```js
const usersContainer = document.querySelector("#users");
const statusText = document.querySelector("#status");

statusText.textContent = "Loading...";

fetch("https://jsonplaceholder.typicode.com/users")
  .then((res) => res.json())
  .then((users) => {
    statusText.textContent = "";

    users.forEach((user) => {
      usersContainer.innerHTML += `
        <div>
          <h3>${user.name}</h3>
          <p>${user.email}</p>
        </div>
      `;
    });
  })
  .catch(() => {
    statusText.textContent = "Failed to load users.";
  });
```

This works, but it is harder to maintain.

---

## Cleaner Version

```js
const usersContainer = document.querySelector("#users");
const statusText = document.querySelector("#status");

const showLoading = () => {
  statusText.textContent = "Loading users...";
};

const showError = () => {
  statusText.textContent = "Failed to load users.";
};

const clearStatus = () => {
  statusText.textContent = "";
};

const fetchUsers = async () => {
  const response = await fetch("https://jsonplaceholder.typicode.com/users");

  // Throwing an error sends the code to the catch block in loadUsers.
  if (!response.ok) {
    throw new Error("Failed to fetch users");
  }

  // Return the data so another function can decide what to do with it.
  return response.json();
};

const renderUsers = (users) => {
  usersContainer.innerHTML = "";

  users.forEach((user) => {
    const card = document.createElement("div");
    card.classList.add("user-card");

    card.innerHTML = `
      <h3>${user.name}</h3>
      <p>${user.email}</p>
    `;

    usersContainer.appendChild(card);
  });
};

const loadUsers = async () => {
  showLoading();

  try {
    // fetchUsers only gets data. It does not touch the page.
    const users = await fetchUsers();

    // renderUsers only displays data. It does not call the API.
    renderUsers(users);
    clearStatus();
  } catch (error) {
    showError();
  }
};

const init = () => {
  // init is the starting point of the app.
  loadUsers();
};

init();
```

---

## Why This Is Better

- `fetchUsers` only fetches data
- `renderUsers` only renders data
- `loadUsers` controls the flow
- `init` starts the app

This prepares students for React later, where separating logic and UI matters a lot.

---

## Naming Rules

Use clear names.

Good:

```js
const usersContainer = document.querySelector("#users");
const renderUsers = () => {};
const fetchPosts = () => {};
```

Not good:

```js
const x = document.querySelector("#users");
const doThing = () => {};
const dataStuff = () => {};
```

---

## Common Mistakes

### Mistake 1: One huge function

Avoid:

```js
const app = async () => {
  // fetch
  // validate
  // render
  // add events
  // update UI
  // handle errors
};
```

Break into small functions.

### Mistake 2: Poor names

Wrong:

```js
const box = document.querySelector("#users");
```

Better:

```js
const usersContainer = document.querySelector("#users");
```

### Mistake 3: Repeating DOM selection

Instead of repeatedly doing:

```js
document.querySelector("#status").textContent = "Loading";
document.querySelector("#status").textContent = "";
document.querySelector("#status").textContent = "Error";
```

Store it once:

```js
const statusText = document.querySelector("#status");
```

---

## Exercises

### Exercise 1

Take yesterday’s API project and create these functions:

- `fetchUsers`
- `renderUsers`
- `showLoading`
- `showError`
- `loadUsers`
- `init`

### Exercise 2

Rename unclear variables.

Example:

```js
const box = document.querySelector("#posts");
```

Change to:

```js
const postsContainer = document.querySelector("#posts");
```

### Exercise 3

Move all JavaScript into `script.js`.

No JavaScript should be inside HTML.

---

## Mini-Task

Refactor API project.

Starter structure:

```js
const statusText = document.querySelector("#status");
const postsContainer = document.querySelector("#posts");

const showLoading = () => {};

const showError = () => {};

const fetchPosts = async () => {};

const renderPosts = (posts) => {};

const loadPosts = async () => {};

const init = () => {};

init();
```

Completed idea:

```js
const statusText = document.querySelector("#status");
const postsContainer = document.querySelector("#posts");

const showLoading = () => {
  statusText.textContent = "Loading posts...";
};

const showError = () => {
  statusText.textContent = "Could not load posts.";
};

const clearStatus = () => {
  statusText.textContent = "";
};

const fetchPosts = async () => {
  const response = await fetch("https://jsonplaceholder.typicode.com/posts");

  if (!response.ok) {
    throw new Error("Failed to fetch posts");
  }

  return response.json();
};

const renderPosts = (posts) => {
  postsContainer.innerHTML = "";

  // Only render the first 5 posts to keep the beginner project small.
  posts.slice(0, 5).forEach((post) => {
    const card = document.createElement("div");
    card.classList.add("post-card");

    card.innerHTML = `
      <h3>${post.title}</h3>
      <p>${post.body}</p>
    `;

    postsContainer.appendChild(card);
  });
};

const loadPosts = async () => {
  showLoading();

  try {
    const posts = await fetchPosts();
    renderPosts(posts);
    clearStatus();
  } catch (error) {
    showError();
  }
};

const init = () => {
  loadPosts();
};

init();
```

---

## 30-Minute Flow

```text
5 min  → Explain clean structure
10 min → Refactor messy example
10 min → Students refactor previous project
5 min  → Review naming and functions
```

---

## Expected Outcome

You can split a small frontend app into clear files and functions so the project is easier to read, debug, and prepare for React.

---

## Navigation

[← Day 11](day-11) | [Day 13–14 →](day-13-14)
