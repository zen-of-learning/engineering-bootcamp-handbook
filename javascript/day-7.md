# Day 7 — DOM Manipulation

> **Goal:** Create elements, add classes, and build a simple Todo UI with JavaScript.

---

## Short Explanation

Changing existing text is useful, but real apps also create new elements. A todo app creates a new list item for each task. `createElement` creates an HTML element in memory. `textContent` fills it with text. `classList.add` applies CSS classes. `appendChild` places the new element on the page. This pattern appears everywhere in frontend work: create an element, add content, style it, and insert it. Today you will build a Todo UI from sample data, without saving anything yet.

---

## Code Examples

`index.html`:

```html
<h1>Todo List</h1>
<ul id="todo-list"></ul>
<script src="script.js"></script>
```

`style.css` idea:

```css
.todo-item {
  padding: 8px;
  margin-bottom: 6px;
  border: 1px solid #ccc;
}

.completed {
  text-decoration: line-through;
  color: gray;
}
```

`script.js`:

```js
const todos = [
  { text: "Practice arrays", isDone: true },
  { text: "Build Todo UI", isDone: false },
  { text: "Review DOM methods", isDone: false }
];

const todoList = document.querySelector("#todo-list");

todos.forEach((todo) => {
  const listItem = document.createElement("li");
  listItem.textContent = todo.text;
  listItem.classList.add("todo-item");

  if (todo.isDone) {
    listItem.classList.add("completed");
  }

  todoList.appendChild(listItem);
});
```

---

## Exercises

1. Create a `li` element with JavaScript and append it to a `ul`.
2. Add a CSS class to the new `li` using `classList.add`.
3. Render at least three tasks from an array.

---

## Mini-Project

Build a simple Todo UI with sample tasks.

Requirements:

- Store tasks in an array
- Render every task into a list
- Add a CSS class to each task
- Add a different class for completed tasks
- No input and no persistence yet

---

## Expected Outcome

You can create DOM elements from data and render a small UI from an array of objects.
---

## Navigation

[← Day 6](day-6) | [Day 8 →](day-8)
