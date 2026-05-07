# Day 9 — Forms and Form Validation

## Goal

Students should learn how to handle form submissions.

---

## Practical Explanation

Forms are everywhere in frontend apps:

- Login
- Signup
- Search
- Checkout
- Contact form
- Newsletter form
- Feedback form

By default, submitting a form refreshes the page.

In JavaScript apps, we usually prevent that using:

```js
event.preventDefault();
```

Then we read the values and validate them.

---

## Basic Form

HTML:

```html
<form id="signup-form">
  <input id="name" type="text" placeholder="Name">
  <input id="email" type="email" placeholder="Email">
  <button type="submit">Sign Up</button>
</form>
<p id="result"></p>
```

JavaScript:

```js
const form = document.querySelector("#signup-form");
const nameInput = document.querySelector("#name");
const emailInput = document.querySelector("#email");
const result = document.querySelector("#result");

form.addEventListener("submit", (event) => {
  event.preventDefault();

  const name = nameInput.value;
  const email = emailInput.value;

  result.textContent = `${name} signed up with ${email}`;
});
```

---

## Why Use Form Submit Instead of Button Click?

This is better:

```js
form.addEventListener("submit", handleSubmit);
```

Because it works when:

- User clicks submit button
- User presses Enter

Button click only handles button click.

---

## Basic Validation

```js
form.addEventListener("submit", (event) => {
  event.preventDefault();

  const name = nameInput.value.trim();
  const email = emailInput.value.trim();

  if (name === "") {
    result.textContent = "Name is required.";
    return;
  }

  if (email === "") {
    result.textContent = "Email is required.";
    return;
  }

  result.textContent = `Thanks for signing up, ${name}!`;
});
```

---

## Email Validation

Simple beginner-friendly version:

```js
if (!email.includes("@")) {
  result.textContent = "Please enter a valid email.";
  return;
}
```

This is not perfect, but good enough for beginners.

---

## Guided Example: Signup Form

HTML:

```html
<form id="signup-form">
  <input id="name" type="text" placeholder="Name">
  <input id="email" type="email" placeholder="Email">
  <input id="password" type="password" placeholder="Password">
  <button type="submit">Create Account</button>
</form>
<p id="message"></p>
```

JavaScript:

```js
const signupForm = document.querySelector("#signup-form");
const nameInput = document.querySelector("#name");
const emailInput = document.querySelector("#email");
const passwordInput = document.querySelector("#password");
const message = document.querySelector("#message");

signupForm.addEventListener("submit", (event) => {
  event.preventDefault();

  const name = nameInput.value.trim();
  const email = emailInput.value.trim();
  const password = passwordInput.value.trim();

  if (!name) {
    message.textContent = "Name is required.";
    return;
  }

  if (!email.includes("@")) {
    message.textContent = "Please enter a valid email.";
    return;
  }

  if (password.length < 8) {
    message.textContent = "Password must be at least 8 characters.";
    return;
  }

  message.textContent = `Account created for ${name}.`;

  nameInput.value = "";
  emailInput.value = "";
  passwordInput.value = "";
});
```

---

## Common Mistakes

### Mistake 1: Forgetting `preventDefault`

Without it, the page refreshes.

```js
event.preventDefault();
```

### Mistake 2: Reading input outside submit handler

Wrong:

```js
const name = nameInput.value;

form.addEventListener("submit", () => {
  console.log(name);
});
```

This reads the value too early.

Correct:

```js
form.addEventListener("submit", () => {
  const name = nameInput.value;
  console.log(name);
});
```

### Mistake 3: Not trimming values

Better:

```js
const name = nameInput.value.trim();
```

---

## Exercises

### Exercise 1

Create a login form with:

- Email
- Password

Validate both are not empty.

### Exercise 2

Create a search form.

When submitted, show:

```text
Searching for: user input
```

### Exercise 3

Create a feedback form with:

- Name
- Message

Message must be at least 10 characters.

---

## Mini-Project

Build a signup form.

Requirements:

- Name required
- Email required
- Email must include `@`
- Password required
- Password minimum 8 characters
- Show success message
- Clear form after success

---

## Expected Outcome

You can prevent form refreshes, read current input values during submit, validate required fields, show useful error messages, and clear successful forms.

---

## Navigation

[← Day 8](day-8) | [Day 10 →](day-10)
