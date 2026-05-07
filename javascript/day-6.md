# Day 6 — DOM Basics

> **Goal:** Select HTML elements and update page content with JavaScript.

---

## Short Explanation

The DOM is the browser's JavaScript-friendly version of your HTML page. JavaScript can select elements, read them, change text, insert HTML, and respond to users. Today, keep it simple: select one element and update what the user sees. `querySelector` finds the first matching element. `textContent` changes plain text. `innerHTML` inserts HTML markup. Use `textContent` for normal text. Use `innerHTML` only when you intentionally want to create HTML. This is the first step from console-only JavaScript to real frontend apps.

---

## Code Examples

`index.html`:

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>DOM Practice</title>
</head>
<body>
  <h1 id="title">Welcome</h1>
  <p class="message">Loading...</p>
  <div id="profile"></div>

  <script src="script.js"></script>
</body>
</html>
```

`script.js`:

```js
const title = document.querySelector("#title");
const message = document.querySelector(".message");
const profile = document.querySelector("#profile");

title.textContent = "JavaScript changed this heading";
message.textContent = "The page is ready.";

profile.innerHTML = `
  <h2>User Profile</h2>
  <p>Name: Lina</p>
  <p>Role: Frontend Student</p>
`;
```

---

## Exercises

1. Select a heading and change its text.
2. Select a paragraph and display your name inside it.
3. Use `innerHTML` to insert a small profile card with a name and city.

---

## Mini-Task

Create a simple webpage with:

- one heading
- one paragraph
- one empty `div`

Use JavaScript to display dynamic text about a user in the empty `div`.

---

## Expected Outcome

You can connect a JavaScript file to an HTML page, select elements, and update visible content in the browser.
---

## Navigation

[← Day 5](day-5) | [Day 7 →](day-7)
