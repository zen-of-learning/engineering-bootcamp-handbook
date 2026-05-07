# Day 1 — JavaScript Basics, Part 1

> **Goal:** Use the browser console, create variables with `let` and `const`, and store simple user data.

---

## Short Explanation

JavaScript makes webpages interactive. HTML gives a page structure, CSS makes it look good, and JavaScript makes it respond to data and user actions. Today you only need the basics: store values, print them, and understand simple data types. Use `const` when a value should not be reassigned. Use `let` when the value may change later. Skip `var` for this bootcamp. Strings are text, numbers are numeric values, and booleans are `true` or `false`. The browser console is your first practice area because it lets you run code quickly. Open DevTools, go to the Console tab, and type each example yourself. The goal is not memorizing syntax; the goal is getting comfortable writing and reading small pieces of code.

---

## Code Examples

```js
const studentName = "Amina";
let studentAge = 19;
const isEnrolled = true;

console.log(studentName);
console.log(studentAge);
console.log(isEnrolled);
```

Use values inside a sentence:

```js
const name = "Leo";
let age = 21;
const city = "Manila";

console.log(`${name} is ${age} years old and lives in ${city}.`);

age = 22;
console.log(`${name} is now ${age}.`);
```

Store multiple simple values:

```js
const firstHobby = "coding";
const secondHobby = "basketball";
const thirdHobby = "music";

console.log("Hobbies:", firstHobby, secondHobby, thirdHobby);
```

---

## Exercises

1. Create `const` variables for your name and city, and a `let` variable for your age.
2. Print one sentence that uses all three variables.
3. Change the age value and print a second sentence with the updated age.

---

## Mini-Task

Store and print user data:

- `name`
- `age`
- `hobbyOne`
- `hobbyTwo`
- `hobbyThree`

Print a short profile that looks like this:

```text
User: Maya
Age: 20
Hobbies: reading, design, cycling
```

---

## Expected Outcome

You can open the browser console, create values with `let` and `const`, print useful messages, and explain the difference between strings, numbers, and booleans.

---

## Navigation

[← JavaScript Overview](index) | [Day 2 →](day-2)
