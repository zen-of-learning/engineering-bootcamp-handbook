# Day 8 — Events: Clicks and Inputs

## Goal

Students should learn how to make pages respond to user actions.

---

## Practical Explanation

Events are actions that happen in the browser.

Common examples:

- User clicks a button
- User types in an input
- User submits a form
- User selects an option
- User scrolls the page

JavaScript listens for these actions using `addEventListener`.

This is one of the most important frontend concepts.

---

## Click Event

HTML:

```html
<button id="click-btn">Click Me</button>
<p id="message"></p>
```

JavaScript:

```js
const button = document.querySelector("#click-btn");
const message = document.querySelector("#message");

button.addEventListener("click", () => {
  message.textContent = "Button clicked!";
});
```

---

## Input Event

HTML:

```html
<input id="name-input" type="text">
<p id="preview"></p>
```

JavaScript:

```js
const nameInput = document.querySelector("#name-input");
const preview = document.querySelector("#preview");

nameInput.addEventListener("input", () => {
  preview.textContent = nameInput.value;
});
```

The `input` event runs every time the user types.

---

## Reading Input Value

```js
const inputValue = nameInput.value;
```

Input values are always strings.

```js
const ageInput = document.querySelector("#age");
console.log(ageInput.value); // "25", not 25
```

Convert to number when needed:

```js
const age = Number(ageInput.value);
```

---

## Guided Example: Add Item on Button Click

HTML:

```html
<input id="item-input" type="text">
<button id="add-btn">Add Item</button>
<ul id="item-list"></ul>
```

JavaScript:

```js
const itemInput = document.querySelector("#item-input");
const addButton = document.querySelector("#add-btn");
const itemList = document.querySelector("#item-list");

addButton.addEventListener("click", () => {
  const itemText = itemInput.value;

  if (itemText === "") {
    return;
  }

  const li = document.createElement("li");
  li.textContent = itemText;

  itemList.appendChild(li);

  itemInput.value = "";
});
```

---

## Improving User Experience

Trim empty spaces:

```js
const itemText = itemInput.value.trim();
```

This prevents input like:

```text
"      "
```

Updated version:

```js
addButton.addEventListener("click", () => {
  const itemText = itemInput.value.trim();

  if (itemText === "") {
    return;
  }

  const li = document.createElement("li");
  li.textContent = itemText;

  itemList.appendChild(li);

  itemInput.value = "";
});
```

---

## Common Mistakes

### Mistake 1: Calling the function immediately

Wrong:

```js
button.addEventListener("click", showMessage());
```

Correct:

```js
button.addEventListener("click", showMessage);
```

Or:

```js
button.addEventListener("click", () => {
  showMessage();
});
```

### Mistake 2: Forgetting `.value`

Wrong:

```js
const name = nameInput;
```

Correct:

```js
const name = nameInput.value;
```

### Mistake 3: Not clearing input after adding item

Better UX:

```js
itemInput.value = "";
```

---

## Exercises

### Exercise 1

Create a button that changes heading text.

### Exercise 2

Create an input that shows live preview text.

### Exercise 3

Create a button that adds a new product name to a list.

---

## Mini-Project

Add tasks to Todo list using input and button.

HTML:

```html
<h1>Todo App</h1>
<input id="task-input" type="text" placeholder="Enter task">
<button id="add-btn">Add Task</button>
<ul id="todo-list"></ul>
```

JavaScript:

```js
const taskInput = document.querySelector("#task-input");
const addButton = document.querySelector("#add-btn");
const todoList = document.querySelector("#todo-list");

const addTask = () => {
  const taskText = taskInput.value.trim();

  if (taskText === "") {
    return;
  }

  const li = document.createElement("li");
  li.textContent = taskText;
  li.classList.add("todo-item");

  todoList.appendChild(li);

  taskInput.value = "";
};

addButton.addEventListener("click", addTask);
```

Bonus: Add task when pressing Enter later with form submission on Day 9.

---

## Expected Outcome

You can listen for clicks and input changes, read input values, create elements from user input, and update the page after user actions.

---

## Navigation

[← Day 7](day-7) | [Day 9 →](day-9)
