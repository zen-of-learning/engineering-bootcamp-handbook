# Day 7 — DOM Manipulation: Creating Elements

## Goal

Students should learn how to create UI elements using JavaScript.

---

## Practical Explanation

So far, we changed existing HTML.

Today, we create new HTML elements using JavaScript.

This matters because real apps often display dynamic lists:

- Todo list
- Product list
- User list
- API results
- Search results
- Comments
- Notifications

Instead of hardcoding every item in HTML, JavaScript can create them.

---

## Key Methods

```text
createElement → creates an HTML element
textContent   → adds text
classList.add → adds CSS class
appendChild   → adds element to the page
```

---

## Basic Example

HTML:

```html
<ul id="todo-list"></ul>
```

JavaScript:

```js
const todoList = document.querySelector("#todo-list");

const li = document.createElement("li");
li.textContent = "Learn JavaScript";

todoList.appendChild(li);
```

---

## Adding Classes

```js
li.classList.add("todo-item");
```

CSS:

```css
.todo-item {
  padding: 10px;
  border-bottom: 1px solid #ddd;
}
```

---

## Creating Multiple Items from an Array

```js
const tasks = ["Study JS", "Practice DOM", "Build Todo App"];
const todoList = document.querySelector("#todo-list");

tasks.forEach((task) => {
  const li = document.createElement("li");
  li.textContent = task;
  li.classList.add("todo-item");

  todoList.appendChild(li);
});
```

---

## Creating Product Cards

HTML:

```html
<div id="products"></div>
```

JavaScript:

```js
const products = [
  { name: "Laptop", price: 1200 },
  { name: "Mouse", price: 25 },
  { name: "Keyboard", price: 75 }
];

const productsContainer = document.querySelector("#products");

products.forEach((product) => {
  const card = document.createElement("div");
  card.classList.add("product-card");

  card.innerHTML = `
    <h3>${product.name}</h3>
    <p>$${product.price}</p>
  `;

  productsContainer.appendChild(card);
});
```

CSS:

```css
.product-card {
  padding: 16px;
  margin-bottom: 12px;
  border: 1px solid #ddd;
  border-radius: 8px;
}
```

---

## Guided Example: Todo UI

HTML:

```html
<h1>Todo App</h1>
<ul id="todo-list"></ul>
```

JavaScript:

```js
const tasks = [
  "Learn variables",
  "Practice functions",
  "Build DOM project"
];

const todoList = document.querySelector("#todo-list");

tasks.forEach((task) => {
  const li = document.createElement("li");
  li.textContent = task;
  li.classList.add("todo-item");

  todoList.appendChild(li);
});
```

CSS:

```css
.todo-item {
  padding: 12px;
  margin-bottom: 8px;
  background: white;
  border: 1px solid #ddd;
  border-radius: 6px;
}
```

---

## Common Mistakes

### Mistake 1: Creating element but not appending it

```js
const li = document.createElement("li");
li.textContent = "Task";
```

This creates the element, but it does not show on the page.

Need:

```js
todoList.appendChild(li);
```

### Mistake 2: Selecting wrong container

```js
const todoList = document.querySelector("#todos");
```

But HTML has:

```html
<ul id="todo-list"></ul>
```

Correct:

```js
const todoList = document.querySelector("#todo-list");
```

### Mistake 3: Repeating too much code

Instead of:

```js
const li1 = document.createElement("li");
const li2 = document.createElement("li");
const li3 = document.createElement("li");
```

Use an array and `forEach`.

---

## Exercises

### Exercise 1

Create a list of 3 cities using JavaScript.

### Exercise 2

Create product cards from an array.

Each card should show:

- Product name
- Price
- Stock status

### Exercise 3

Add a CSS class to every created card.

---

## Mini-Project

Build a simple Todo UI.

HTML:

```html
<h1>Todo App</h1>
<ul id="todo-list"></ul>
```

JavaScript:

```js
const tasks = [
  { title: "Learn JavaScript basics", completed: false },
  { title: "Practice DOM", completed: false },
  { title: "Build Todo UI", completed: true }
];

const todoList = document.querySelector("#todo-list");

tasks.forEach((task) => {
  const li = document.createElement("li");
  li.classList.add("todo-item");

  li.innerHTML = `
    <span>${task.title}</span>
    <strong>${task.completed ? "Done" : "Pending"}</strong>
  `;

  todoList.appendChild(li);
});
```

---

## 30-Minute Flow

```text
5 min  → Explain dynamic UI
10 min → createElement, classList, appendChild
10 min → Product/list exercises
10 min → Todo UI mini-project
```

---

## Expected Outcome

You can create new HTML elements with JavaScript, add text and classes, append them to the page, and render simple lists from arrays.

---

## Navigation

[← Day 6](day-6) | [Day 8 →](day-8)
