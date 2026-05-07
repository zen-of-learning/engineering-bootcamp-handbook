# Day 3 — Control Flow + Functions

> **Goal:** Make decisions with `if/else` and reuse logic with functions.

---

## Short Explanation

Apps need decisions. A signup form may reject an empty email. A dashboard may show different messages for active and inactive users. `if/else` lets your code choose what to do. Comparison operators help you ask questions like “is this age greater than or equal to 18?” Functions let you reuse a task instead of writing the same code again. A function can receive input, run logic, and return a result. Normal functions and arrow functions are both common in modern JavaScript. Today, focus on reading them and writing small practical functions.

---

## Code Examples

Control flow:

```js
const age = 19;

if (age >= 18) {
  console.log("Access allowed");
} else {
  console.log("You must be 18 or older");
}
```

Normal function:

```js
function getGreeting(name) {
  return `Welcome, ${name}!`;
}

const message = getGreeting("Nora");
console.log(message);
```

Arrow function:

```js
const isAdult = (age) => {
  return age >= 18;
};

console.log(isAdult(16));
console.log(isAdult(21));
```

Practical validation:

```js
function validateAge(name, age) {
  if (age >= 18) {
    return `${name} can create an account.`;
  }

  return `${name} needs permission from a parent or guardian.`;
}

console.log(validateAge("Mina", 17));
```

---

## Exercises

1. Write an `if/else` statement that checks if a product price is greater than 100.
2. Write a function named `createWelcomeMessage` that returns a greeting for a user.
3. Convert a normal `addNumbers` function into an arrow function.

---

## Mini-Task

Create a function named `validateUserAge` that accepts `name` and `age`.

It should return:

- `"Name can sign up"` if the user is 18 or older
- `"Name cannot sign up yet"` if the user is under 18

Call the function with three different users and print the results.

---

## Expected Outcome

You can write simple decision logic, create reusable functions, return values, and use functions for real validation tasks.
---

## Navigation

[← Day 2](day-2) | [Day 4 →](day-4)
