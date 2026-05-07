# Day 3 — Control Flow and Functions

## Goal

Students should learn how to make decisions and reuse code.

---

## Practical Explanation

Real apps make decisions all the time.

Examples:

- If user is logged in, show dashboard.
- If cart is empty, show empty cart message.
- If password is too short, show error.
- If API fails, show error message.

This is where `if/else` and functions become important.

---

## Comparison Operators

```js
const age = 18;

console.log(age > 18);  // false
console.log(age >= 18); // true
console.log(age === 18); // true
console.log(age !== 21); // true
```

Common operators:

```text
>    greater than
<    less than
>=   greater than or equal
<=   less than or equal
===  equal value
!==  not equal value
```

Use `===` instead of `==`.

---

## If/Else

```js
const age = 20;

if (age >= 18) {
  console.log("User can sign up.");
} else {
  console.log("User is too young.");
}
```

---

## Multiple Conditions

```js
const score = 85;

if (score >= 90) {
  console.log("Grade A");
} else if (score >= 80) {
  console.log("Grade B");
} else if (score >= 70) {
  console.log("Grade C");
} else {
  console.log("Needs improvement");
}
```

---

## Functions

A function stores reusable logic.

```js
function greetUser(name) {
  console.log(`Hello, ${name}`);
}

greetUser("Alex");
greetUser("Maya");
```

---

## Return Values

Use `return` when you want the function to give back a value.

```js
function add(a, b) {
  return a + b;
}

const total = add(5, 3);

console.log(total);
```

---

## Arrow Functions

Common in modern frontend code.

```js
const greetUser = (name) => {
  return `Hello, ${name}`;
};

console.log(greetUser("Sam"));
```

Short version:

```js
const add = (a, b) => a + b;
```

---

## Guided Example

Validate user age.

```js
const validateAge = (age) => {
  if (age >= 18) {
    return "User can create an account.";
  }

  return "User must be at least 18.";
};

console.log(validateAge(20));
console.log(validateAge(15));
```

---

## Another Real-World Example

Validate password length.

```js
const validatePassword = (password) => {
  if (password.length >= 8) {
    return "Password is valid.";
  }

  return "Password must be at least 8 characters.";
};

console.log(validatePassword("abc"));
console.log(validatePassword("strongpass"));
```

---

## Common Mistakes

### Mistake 1: Using `=` instead of `===`

Wrong:

```js
if (age = 18) {
  console.log("Allowed");
}
```

Correct:

```js
if (age === 18) {
  console.log("Allowed");
}
```

### Mistake 2: Forgetting to call the function

```js
const greet = () => {
  console.log("Hello");
};

greet; // Does nothing
```

Correct:

```js
greet();
```

### Mistake 3: Forgetting `return`

Wrong:

```js
const add = (a, b) => {
  a + b;
};
```

Correct:

```js
const add = (a, b) => {
  return a + b;
};
```

Or:

```js
const add = (a, b) => a + b;
```

---

## Exercises

### Exercise 1

Write a function called `isAdult`.

It should return:

- `Adult`
- `Minor`

Based on age.

### Exercise 2

Write a function called `getDiscount`.

Rules:

```text
price >= 100 → "You get 20% discount"
price >= 50  → "You get 10% discount"
otherwise    → "No discount"
```

### Exercise 3

Write an arrow function that takes first name and last name, then returns full name.

---

## Mini-Task

Validate signup input.

```js
const validateSignup = (name, age) => {
  if (!name) {
    return "Name is required.";
  }

  if (age < 18) {
    return "User must be at least 18.";
  }

  return "Signup successful.";
};

console.log(validateSignup("Alex", 22));
console.log(validateSignup("", 22));
console.log(validateSignup("Sam", 15));
```

---

## 30-Minute Flow

```text
5 min  → Explain if/else and comparisons
10 min → Function examples
10 min → Exercises
5 min  → Signup validation mini-task
```

---

## Expected Outcome

You can compare values, write `if/else` decisions, create reusable functions, return results, and validate basic signup input.

---

## Navigation

[← Day 2](day-2) | [Day 4 →](day-4)
