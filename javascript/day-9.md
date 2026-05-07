# Day 9 — Forms

> **Goal:** Handle form submission, prevent page refresh, read inputs, and show validation messages.

---

## Short Explanation

Forms are used for signup, login, checkout, search, feedback, and settings. By default, submitting a form refreshes the page. In frontend apps, you usually prevent that with `event.preventDefault()` so JavaScript can handle the data. Read input values from the form, validate them, then show a message. Keep validation simple today: make sure required fields are not empty. This pattern prepares you for sending form data to APIs later.

---

## Code Examples

`index.html`:

```html
<form id="signup-form">
  <label>
    Name
    <input id="name-input" type="text">
  </label>

  <label>
    Email
    <input id="email-input" type="email">
  </label>

  <button type="submit">Sign Up</button>
</form>

<p id="form-message"></p>
<script src="script.js"></script>
```

`script.js`:

```js
const form = document.querySelector("#signup-form");
const nameInput = document.querySelector("#name-input");
const emailInput = document.querySelector("#email-input");
const formMessage = document.querySelector("#form-message");

form.addEventListener("submit", (event) => {
  event.preventDefault();

  const name = nameInput.value;
  const email = emailInput.value;

  if (name === "" || email === "") {
    formMessage.textContent = "Please enter both name and email.";
    return;
  }

  formMessage.textContent = `Thanks for signing up, ${name}!`;
  form.reset();
});
```

---

## Exercises

1. Read name and email values from a form.
2. Show a success message after valid submission.
3. Show an error message when either field is empty.

---

## Mini-Project

Build a simple signup form with:

- name input
- email input
- submit button
- success message
- basic empty-field validation

Bonus: Add a `role` dropdown and include the selected role in the success message.

---

## Expected Outcome

You can handle form submissions without refreshing the page and display useful validation feedback.

---

## Navigation

[← Day 8](day-8) | [Day 10 →](day-10)
