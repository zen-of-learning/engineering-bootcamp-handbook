# Day 11 — API Data + UI Rendering

## Goal

Students should learn how to fetch API data and display it on a webpage.

---

## Practical Explanation

Calling an API is not enough.

In real frontend apps, you usually need to:

- Show loading state
- Fetch data
- Convert response to JSON
- Display data in UI
- Handle errors

This is one of the most important frontend workflows.

---

## HTML Setup

```html
<h1>Users</h1>
<p id="status"></p>
<div id="users"></div>
```

---

## Basic API to UI Example

```js
const statusText = document.querySelector("#status");
const usersContainer = document.querySelector("#users");

const fetchUsers = async () => {
  // Tell users something is happening while the API request is running.
  statusText.textContent = "Loading users...";

  try {
    const response = await fetch("https://jsonplaceholder.typicode.com/users");
    const users = await response.json();

    // Clear old content before rendering new content.
    usersContainer.innerHTML = "";

    users.forEach((user) => {
      const card = document.createElement("div");
      card.classList.add("user-card");

      // innerHTML is useful here because each card needs multiple HTML elements.
      card.innerHTML = `
        <h3>${user.name}</h3>
        <p>${user.email}</p>
        <p>${user.address.city}</p>
      `;

      usersContainer.appendChild(card);
    });

    // Remove the loading message after users render successfully.
    statusText.textContent = "";
  } catch (error) {
    statusText.textContent = "Failed to load users.";
  }
};

fetchUsers();
```

---

## CSS

```css
.user-card {
  padding: 16px;
  margin-bottom: 12px;
  border: 1px solid #ddd;
  border-radius: 8px;
  background: white;
}
```

---

## Separate Render Function

Better structure:

```js
const renderUsers = (users) => {
  usersContainer.innerHTML = "";

  users.forEach((user) => {
    const card = document.createElement("div");
    card.classList.add("user-card");

    card.innerHTML = `
      <h3>${user.name}</h3>
      <p>Email: ${user.email}</p>
      <p>City: ${user.address.city}</p>
    `;

    usersContainer.appendChild(card);
  });
};
```

Then use it:

```js
const fetchUsers = async () => {
  statusText.textContent = "Loading users...";

  try {
    const response = await fetch("https://jsonplaceholder.typicode.com/users");
    const users = await response.json();

    // Keep rendering logic in its own function so fetchUsers stays focused.
    renderUsers(users);

    statusText.textContent = "";
  } catch (error) {
    statusText.textContent = "Failed to load users.";
  }
};
```

---

## Guided Example: Display Posts

HTML:

```html
<h1>Posts</h1>
<p id="status"></p>
<div id="posts"></div>
```

JavaScript:

```js
const postsContainer = document.querySelector("#posts");
const statusText = document.querySelector("#status");

const renderPosts = (posts) => {
  postsContainer.innerHTML = "";

  posts.forEach((post) => {
    const card = document.createElement("div");
    card.classList.add("post-card");

    card.innerHTML = `
      <h3>${post.title}</h3>
      <p>${post.body}</p>
    `;

    postsContainer.appendChild(card);
  });
};

const fetchPosts = async () => {
  statusText.textContent = "Loading posts...";

  try {
    const response = await fetch("https://jsonplaceholder.typicode.com/posts");

    // Check response.ok before trying to render the data.
    if (!response.ok) {
      throw new Error("Failed to fetch posts");
    }

    const posts = await response.json();

    // Display only 10 posts so the page does not become too long.
    renderPosts(posts.slice(0, 10));

    statusText.textContent = "";
  } catch (error) {
    statusText.textContent = error.message;
  }
};

fetchPosts();
```

---

## Common Mistakes

### Mistake 1: Forgetting to clear container

If you call render multiple times, items may duplicate.

Use:

```js
container.innerHTML = "";
```

### Mistake 2: Rendering before data arrives

Wrong:

```js
const users = fetchUsers();
renderUsers(users);
```

Need to wait for data inside async flow.

### Mistake 3: Not showing error message

Always show something when API fails.

```js
statusText.textContent = "Failed to load data.";
```

---

## Exercises

### Exercise 1

Fetch users and display:

- Name
- Email
- Company name

### Exercise 2

Fetch posts and display only first 6 posts.

### Exercise 3

Add loading and error messages.

---

## Mini-Project

Build an API users page.

Requirements:

- Show `"Loading users..."`
- Fetch users
- Display user cards
- Each card shows name, email, city
- Show error message if failed
- Use a separate `renderUsers` function

---

## Expected Outcome

You can fetch API data, show loading and error states, and render API results into visible UI elements.

---

## Navigation

[← Day 10](day-10) | [Day 12 →](day-12)
