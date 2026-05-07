# Day 8 — Events

> **Goal:** Use event listeners to respond to clicks and input changes.

---

## Short Explanation

Events are how users talk to your app. A click, keypress, input change, and form submission are all events. `addEventListener` lets you run code when an event happens. Click events are useful for buttons. Input events are useful when you want to react while the user types. Today you will make yesterday's Todo UI interactive by reading an input value and adding a new task when a button is clicked. This is a critical frontend skill because almost every app depends on user actions.

---

## Code Examples

`index.html`:

```html
<h1>Todo List</h1>
<input id="task-input" type="text" placeholder="Enter a task">
<button id="add-task-button">Add Task</button>
<p id="preview"></p>
<ul id="todo-list"></ul>
<script src="script.js"></script>
```

`script.js`:

```js
const taskInput = document.querySelector("#task-input");
const addTaskButton = document.querySelector("#add-task-button");
const todoList = document.querySelector("#todo-list");
const preview = document.querySelector("#preview");

taskInput.addEventListener("input", () => {
  preview.textContent = `Typing: ${taskInput.value}`;
});

addTaskButton.addEventListener("click", () => {
  const taskText = taskInput.value;

  if (taskText === "") {
    return;
  }

  const listItem = document.createElement("li");
  listItem.textContent = taskText;
  todoList.appendChild(listItem);

  taskInput.value = "";
  preview.textContent = "";
});
```

---

## Exercises

1. Log `"Button clicked"` when a button is clicked.
2. Display live input text in a paragraph as the user types.
3. Clear the input after adding an item to the page.

---

## Mini-Project

Add tasks to the Todo list using an input and button.

Requirements:

- Read the input value
- Ignore empty tasks
- Create a new `li`
- Append it to the list
- Clear the input after adding

---

## Expected Outcome

You can connect user actions to JavaScript and update the page based on clicks and typed input.
---

## Navigation

[← Day 7](day-7) | [Day 9 →](day-9)
