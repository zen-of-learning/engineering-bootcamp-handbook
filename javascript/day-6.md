# Day 6 — DOM Basics

## Goal

Students should learn how JavaScript connects to HTML.

---

## Practical Explanation

The DOM is the browser’s live version of your HTML.

When you write:

```html
<h1>Hello</h1>
```

The browser creates a JavaScript-accessible version of that element.

JavaScript can then:

- Read it
- Change it
- Hide it
- Create new elements
- React to clicks
- Display API data

This is where JavaScript starts feeling like real frontend development.

---

## Basic HTML

```html
<h1 id="title">Welcome</h1>
<p class="message">This is the old message.</p>
<div id="content"></div>
```

---

## Selecting Elements

Use `querySelector`.

```js
const title = document.querySelector("#title");
const message = document.querySelector(".message");
const content = document.querySelector("#content");
```

Selectors work like CSS:

```text
#title    → id
.message  → class
h1        → tag
```

---

## Changing Text

Use `textContent`.

```js
const title = document.querySelector("#title");

title.textContent = "Welcome to JavaScript";
```

---

## Changing HTML

Use `innerHTML`.

```js
const content = document.querySelector("#content");

content.innerHTML = `
  <h2>User Profile</h2>
  <p>Name: Alex</p>
  <p>Role: Frontend Student</p>
`;
```

Use `textContent` for simple text.  
Use `innerHTML` when adding HTML structure.

---

## Guided Example

HTML:

```html
<h1 id="page-title">Old Title</h1>
<p id="description">Old description</p>
<div id="user-card"></div>
```

JavaScript:

```js
const pageTitle = document.querySelector("#page-title");
const description = document.querySelector("#description");
const userCard = document.querySelector("#user-card");

pageTitle.textContent = "User Dashboard";
description.textContent = "Here is the current user information.";

const user = {
  name: "Maya",
  email: "maya@example.com",
  city: "Dallas"
};

userCard.innerHTML = `
  <h2>${user.name}</h2>
  <p>Email: ${user.email}</p>
  <p>City: ${user.city}</p>
`;
```

---

## Real-World Example

Display a product.

HTML:

```html
<div id="product"></div>
```

JavaScript:

```js
const product = {
  name: "Laptop",
  price: 1200,
  inStock: true
};

const productContainer = document.querySelector("#product");

productContainer.innerHTML = `
  <h2>${product.name}</h2>
  <p>Price: $${product.price}</p>
  <p>Status: ${product.inStock ? "Available" : "Out of Stock"}</p>
`;
```

---

## Common Mistakes

### Mistake 1: Wrong selector

HTML:

```html
<h1 id="title">Hello</h1>
```

Wrong:

```js
document.querySelector("title");
```

Correct:

```js
document.querySelector("#title");
```

### Mistake 2: JavaScript runs before HTML exists

Put the script before the closing `body` tag:

```html
<body>
  <h1 id="title">Hello</h1>

  <script src="script.js"></script>
</body>
```

### Mistake 3: Using `innerHTML` for simple text

This works:

```js
title.innerHTML = "Hello";
```

But better:

```js
title.textContent = "Hello";
```

---

## Exercises

### Exercise 1

Create an `h1` with id `main-title`.

Use JavaScript to change its text.

### Exercise 2

Create a `div` with id `profile`.

Use `innerHTML` to display:

- Name
- Email
- City

### Exercise 3

Create a product object and display it in the browser.

---

## Mini-Task

Display dynamic text on a webpage.

HTML:

```html
<h1 id="welcome"></h1>
<p id="description"></p>
<div id="profile"></div>
```

JavaScript:

```js
const user = {
  name: "Nina",
  role: "Frontend Student",
  city: "Austin"
};

document.querySelector("#welcome").textContent = `Welcome, ${user.name}`;
document.querySelector("#description").textContent = "You are learning DOM basics.";

document.querySelector("#profile").innerHTML = `
  <h2>${user.name}</h2>
  <p>Role: ${user.role}</p>
  <p>City: ${user.city}</p>
`;
```

---

## 30-Minute Flow

```text
5 min  → Explain DOM
10 min → querySelector, textContent, innerHTML
10 min → Exercises
5 min  → Dynamic profile mini-task
```

---

## Expected Outcome

You can explain what the DOM is, select HTML elements with JavaScript, update simple text, and render basic HTML from data.

---

## Navigation

[← Day 5](day-5) | [Day 7 →](day-7)
