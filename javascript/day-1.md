# Day 1 — JavaScript Basics: Variables, Data Types, Console

## Goal

Students should learn how to store simple values, print them, and understand basic JavaScript data types.

By the end of the day, students should be able to write:

```js
const name = "Alex";
let age = 22;

console.log(name);
console.log(age);
```

---

## Practical Explanation

JavaScript is used to make websites interactive.

HTML gives the page structure.  
CSS makes the page look good.  
JavaScript makes the page do things.

Example:

```text
HTML  → Button exists
CSS   → Button looks nice
JS    → Button does something when clicked
```

In JavaScript, we store data using variables.

Use `const` when the value should stay the same.

```js
const name = "Alex";
```

Use `let` when the value can change.

```js
let score = 0;
score = 10;
```

Do not use `var` in this bootcamp. It is older and can confuse beginners.

---

## Core Concepts

### `const`

Use when you do not plan to reassign the variable.

```js
const appName = "Todo App";
console.log(appName);
```

You cannot do this:

```js
const appName = "Todo App";
appName = "Weather App"; // Error
```

### `let`

Use when the value can change.

```js
let count = 0;

count = count + 1;
count = count + 1;

console.log(count); // 2
```

---

## Basic Data Types

### String

Text value.

```js
const name = "Maya";
const city = "Dallas";
```

### Number

Used for age, price, score, quantity, etc.

```js
const age = 25;
const price = 19.99;
```

### Boolean

True or false value.

```js
const isLoggedIn = true;
const isAdmin = false;
```

### Undefined

A variable exists, but no value has been assigned.

```js
let email;

console.log(email); // undefined
```

### Null

Intentionally empty.

```js
const selectedUser = null;
```

Use `null` when you want to clearly say:

> There is no value right now.

---

## Console Usage

The console is used to test your code.

```js
console.log("Hello JavaScript");
console.log(10);
console.log(true);
```

You can also print labels:

```js
const name = "Alex";
const age = 22;

console.log("Name:", name);
console.log("Age:", age);
```

---

## Guided Example

Create a user profile.

```js
const firstName = "Alex";
const lastName = "Johnson";
let age = 22;
const isStudent = true;

console.log("First Name:", firstName);
console.log("Last Name:", lastName);
console.log("Age:", age);
console.log("Student:", isStudent);
```

Now update the age:

```js
age = 23;

console.log("Updated Age:", age);
```

---

## Template Strings

Instead of this:

```js
console.log(firstName + " is " + age + " years old.");
```

Use this:

```js
console.log(`${firstName} is ${age} years old.`);
```

This is cleaner and commonly used in real projects.

---

## Common Mistakes

### Mistake 1: Reassigning `const`

```js
const age = 22;
age = 23; // Error
```

Use `let` instead:

```js
let age = 22;
age = 23;
```

### Mistake 2: Forgetting quotes for strings

Wrong:

```js
const name = Alex;
```

Correct:

```js
const name = "Alex";
```

### Mistake 3: Confusing string and number

```js
const age = "22";
```

This is a string, not a number.

Better:

```js
const age = 22;
```

---

## Exercises

### Exercise 1

Create variables for a user:

- `name`
- `age`
- `city`
- `isLoggedIn`

Print each one.

### Exercise 2

Create variables for a product:

- `productName`
- `price`
- `inStock`
- `quantity`

Print a sentence like:

```text
Laptop costs $1200
```

### Exercise 3

Create a score counter.

Start with:

```js
let score = 0;
```

Then increase it three times.

Expected result:

```text
Final score: 3
```

---

## Mini-Task

Create and print user data.

```js
const userName = "Sam";
let userAge = 20;
const userCity = "Austin";
const isMember = true;

console.log("User Profile");
console.log("Name:", userName);
console.log("Age:", userAge);
console.log("City:", userCity);
console.log("Member:", isMember);

userAge = 21;

console.log(`${userName} is now ${userAge} years old.`);
```

---

## 30-Minute Flow

```text
5 min  → Explain const, let, and data types
10 min → Code user profile example
10 min → Exercises
5 min  → Mini-task review
```

---

## Expected Outcome

You can store simple values, print them with useful labels, recognize basic JavaScript data types, and use `const` or `let` correctly.

---

## Navigation

[← JavaScript Overview](index) | [Day 2 →](day-2)
