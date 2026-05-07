# Day 10 — Async JavaScript and Fetch

## Goal

Students should learn how to call APIs using `fetch`, `async/await`, and `try/catch`.

---

## Practical Explanation

Frontend apps often need data from a backend or API.

Examples:

- Get users
- Get products
- Get posts
- Get weather
- Get messages
- Get notifications

JavaScript uses `fetch` to call APIs.

For this bootcamp, students do not need deep Promise theory yet.

They need this practical pattern:

```js
const getData = async () => {
  try {
    // fetch sends a request to the API URL and waits for the response.
    const response = await fetch("API_URL");

    // response.json() converts the API response into usable JavaScript data.
    const data = await response.json();

    console.log(data);
  } catch (error) {
    // catch runs if the request or JSON conversion fails.
    console.log("Something went wrong:", error);
  }
};
```

---

## What Is an API?

An API is a URL that gives data.

Example:

```text
https://jsonplaceholder.typicode.com/users
```

When called, it returns user data.

---

## Basic Fetch

```js
fetch("https://jsonplaceholder.typicode.com/users")
  .then((response) => response.json())
  .then((data) => console.log(data));
```

But for this bootcamp, prefer `async/await`.

---

## Async/Await Version

```js
const getUsers = async () => {
  // Wait for the API to respond before moving to the next line.
  const response = await fetch("https://jsonplaceholder.typicode.com/users");

  // Wait for the response body to be converted into JavaScript data.
  const users = await response.json();

  console.log(users);
};

getUsers();
```

---

## Add Try/Catch

```js
const getUsers = async () => {
  try {
    // This request may fail if the network is down or the URL is wrong.
    const response = await fetch("https://jsonplaceholder.typicode.com/users");
    const users = await response.json();

    console.log(users);
  } catch (error) {
    // Show a helpful message instead of letting the app fail silently.
    console.log("Failed to fetch users:", error);
  }
};

getUsers();
```

---

## Checking Response Status

A better version:

```js
const getUsers = async () => {
  try {
    const response = await fetch("https://jsonplaceholder.typicode.com/users");

    // fetch only rejects for network errors, so manually check bad HTTP responses.
    if (!response.ok) {
      throw new Error("Failed to fetch users");
    }

    const users = await response.json();

    console.log(users);
  } catch (error) {
    // error.message gives the message from the Error we created above.
    console.log(error.message);
  }
};

getUsers();
```

---

## Guided Example: Fetch Posts

```js
const getPosts = async () => {
  try {
    const response = await fetch("https://jsonplaceholder.typicode.com/posts");

    // Stop early if the API returns an unsuccessful status.
    if (!response.ok) {
      throw new Error("Failed to fetch posts");
    }

    const posts = await response.json();

    // Show only the first 5 posts so the console stays readable.
    console.log(posts.slice(0, 5));
  } catch (error) {
    console.log("Error:", error.message);
  }
};

getPosts();
```

---

## Common Mistakes

### Mistake 1: Forgetting `await`

Wrong:

```js
const response = fetch("https://jsonplaceholder.typicode.com/users");
```

Correct:

```js
const response = await fetch("https://jsonplaceholder.typicode.com/users");
```

### Mistake 2: Forgetting `.json()`

Wrong:

```js
console.log(response);
```

Correct:

```js
const data = await response.json();
console.log(data);
```

### Mistake 3: Using `await` outside async function

Wrong:

```js
const response = await fetch(url);
```

Correct:

```js
const getData = async () => {
  const response = await fetch(url);
};
```

---

## Exercises

### Exercise 1

Fetch users from:

```text
https://jsonplaceholder.typicode.com/users
```

Print all users.

### Exercise 2

Fetch posts from:

```text
https://jsonplaceholder.typicode.com/posts
```

Print only the first 5 post titles.

### Exercise 3

Fetch one user:

```text
https://jsonplaceholder.typicode.com/users/1
```

Print:

- Name
- Email
- City

---

## Mini-Task

Fetch data from a public API and log useful fields.

```js
const getUser = async () => {
  try {
    const response = await fetch("https://jsonplaceholder.typicode.com/users/1");

    // If the API response is not successful, create an error on purpose.
    if (!response.ok) {
      throw new Error("Could not fetch user");
    }

    const user = await response.json();

    // Log specific fields instead of logging the whole object every time.
    console.log("Name:", user.name);
    console.log("Email:", user.email);
    console.log("City:", user.address.city);
  } catch (error) {
    console.log(error.message);
  }
};

getUser();
```

---

## 30-Minute Flow

```text
5 min  → Explain API/fetch
10 min → async/await examples
10 min → Exercises
5 min  → Mini-task review
```

---

## Expected Outcome

You can call a public API, wait for data with `async/await`, convert the response to JSON, check for bad responses, and handle errors with `try/catch`.

---

## Navigation

[← Day 9](day-9) | [Day 11 →](day-11)
