# Day 10 — Async JavaScript

> **Goal:** Use `fetch`, `async/await`, and `try/catch` to load data from a public API.

---

## Short Explanation

Frontend apps often need data from a server. `fetch` sends a request from the browser to an API. Because API requests take time, JavaScript must wait for the response. `async` and `await` make waiting easier to read. `try/catch` lets you handle errors without crashing your app. You do not need deep Promise theory today. Focus on the practical flow: request data, convert the response to JSON, use the data, and handle errors. JSONPlaceholder is a safe practice API for users, posts, and comments.

---

## Code Examples

Fetch one user:

```js
async function loadUser() {
  try {
    const response = await fetch("https://jsonplaceholder.typicode.com/users/1");
    const user = await response.json();

    console.log(user);
    console.log(user.name);
  } catch (error) {
    console.log("Something went wrong:", error);
  }
}

loadUser();
```

Fetch posts:

```js
async function loadPosts() {
  try {
    const response = await fetch("https://jsonplaceholder.typicode.com/posts");
    const posts = await response.json();

    console.log(posts.slice(0, 5));
  } catch (error) {
    console.log("Could not load posts.");
  }
}

loadPosts();
```

Handle bad responses:

```js
async function loadMissingPage() {
  try {
    const response = await fetch("https://jsonplaceholder.typicode.com/bad-url");

    if (!response.ok) {
      throw new Error("API request failed");
    }

    const data = await response.json();
    console.log(data);
  } catch (error) {
    console.log(error.message);
  }
}
```

---

## Exercises

1. Fetch one user and log the user's name and email.
2. Fetch posts and log only the first three post titles.
3. Fetch a bad URL and show a helpful error message in the console.

---

## Mini-Task

Fetch data from JSONPlaceholder and log it clearly.

Requirements:

- Use an `async` function
- Use `await fetch(...)`
- Convert the response with `response.json()`
- Use `try/catch`
- Log at least three useful fields from the data

---

## Expected Outcome

You can call an API from the browser, wait for the response, read JSON, and handle basic errors.
---

## Navigation

[← Day 9](day-9) | [Day 11 →](day-11)
