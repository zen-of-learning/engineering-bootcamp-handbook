# Day 2 — JavaScript Basics, Part 2

> **Goal:** Store related data using arrays and objects, then read values from them.

---

## Short Explanation

Real apps rarely use one variable at a time. A user may have many hobbies, and a product may have a name, price, and category. Arrays store lists. Objects store related information using property names. `null` means you intentionally have no value yet. `undefined` usually means a value has not been assigned. Use arrays when order matters or when you have many of the same kind of item. Use objects when you want to describe one thing with multiple properties. Today you will combine both: a user object with a hobbies array. This is the same kind of data shape you will see from APIs later.

---

## Code Examples

Arrays:

```js
const hobbies = ["coding", "football", "music"];

console.log(hobbies[0]);
console.log(hobbies[1]);
console.log(hobbies.length);
```

Objects:

```js
const user = {
  name: "Sara",
  age: 22,
  isActive: true
};

console.log(user.name);
console.log(user.age);
console.log(`${user.name} is ${user.age} years old.`);
```

Arrays inside objects:

```js
const student = {
  name: "Kai",
  age: 18,
  email: null,
  hobbies: ["drawing", "gaming", "coding"]
};

console.log(student.hobbies[0]);
console.log(student.email);
```

---

## Exercises

1. Create a `hobbies` array with at least three hobbies and print the first hobby.
2. Create a `user` object with `name`, `age`, `city`, and `isStudent`.
3. Print a summary sentence using values from the object.

---

## Mini-Task

Expand yesterday's user data into one object:

```js
const user = {
  name: "Maya",
  age: 20,
  city: "Cebu",
  hobbies: ["reading", "design", "cycling"]
};
```

Then print:

- the user's name
- the user's city
- the first hobby
- a full profile sentence

---

## Expected Outcome

You can choose between arrays and objects, read values from both, and recognize basic data shapes used in frontend apps and APIs.
---

## Navigation

[← Day 1](day-1) | [Day 3 →](day-3)
