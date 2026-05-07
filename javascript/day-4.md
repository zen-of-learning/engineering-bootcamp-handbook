# Day 4 — Arrays: map, filter, find, forEach

## Goal

Students should learn the most useful array methods for frontend work.

---

## Practical Explanation

Frontend apps constantly display lists.

Examples:

- List of users
- List of products
- List of posts
- List of comments
- List of tasks
- List of notifications

Array methods help us work with these lists.

The four most important methods for this bootcamp are:

```text
forEach → do something for each item
map     → create a new transformed array
filter  → keep only matching items
find    → get the first matching item
```

---

## Starting Data

```js
const users = [
  { id: 1, name: "Alex", active: true, role: "admin" },
  { id: 2, name: "Maya", active: false, role: "user" },
  { id: 3, name: "Sam", active: true, role: "user" },
  { id: 4, name: "Nina", active: true, role: "manager" }
];
```

---

## forEach

Use when you want to do something with each item.

```js
users.forEach((user) => {
  console.log(user.name);
});
```

Good for:

- Printing values
- Creating DOM elements
- Running side effects

---

## map

Use when you want to create a new array.

```js
const names = users.map((user) => {
  return user.name;
});

console.log(names);
```

Short version:

```js
const names = users.map((user) => user.name);
```

Result:

```js
["Alex", "Maya", "Sam", "Nina"]
```

---

## filter

Use when you want only matching items.

```js
const activeUsers = users.filter((user) => {
  return user.active === true;
});

console.log(activeUsers);
```

Shorter:

```js
const activeUsers = users.filter((user) => user.active);
```

---

## find

Use when you want one item.

```js
const adminUser = users.find((user) => {
  return user.role === "admin";
});

console.log(adminUser);
```

Result:

```js
{ id: 1, name: "Alex", active: true, role: "admin" }
```

---

## Combining Methods

Get names of active users.

```js
const activeUserNames = users
  .filter((user) => user.active)
  .map((user) => user.name);

console.log(activeUserNames);
```

Result:

```js
["Alex", "Sam", "Nina"]
```

This pattern is very common in frontend apps.

---

## Real-World Product Example

```js
const products = [
  { id: 1, name: "Laptop", price: 1200, category: "electronics" },
  { id: 2, name: "Mouse", price: 25, category: "electronics" },
  { id: 3, name: "Notebook", price: 10, category: "stationery" },
  { id: 4, name: "Keyboard", price: 75, category: "electronics" }
];

const cheapProducts = products.filter((product) => product.price < 100);

console.log(cheapProducts);
```

Get product names:

```js
const productNames = products.map((product) => product.name);

console.log(productNames);
```

Find one product:

```js
const laptop = products.find((product) => product.name === "Laptop");

console.log(laptop);
```

---

## Common Mistakes

### Mistake 1: Using `map` when you need `filter`

Wrong:

```js
const activeUsers = users.map((user) => user.active);
```

This gives booleans:

```js
[true, false, true, true]
```

Correct:

```js
const activeUsers = users.filter((user) => user.active);
```

### Mistake 2: Forgetting `return`

Wrong:

```js
const names = users.map((user) => {
  user.name;
});
```

Correct:

```js
const names = users.map((user) => {
  return user.name;
});
```

Or:

```js
const names = users.map((user) => user.name);
```

### Mistake 3: Expecting `find` to return many items

```js
const activeUser = users.find((user) => user.active);
```

This returns only the first active user.

Use `filter` for many.

---

## Exercises

### Exercise 1

Given:

```js
const students = [
  { name: "Alex", grade: 85 },
  { name: "Maya", grade: 92 },
  { name: "Sam", grade: 67 },
  { name: "Nina", grade: 74 }
];
```

Use `filter` to get students with grade above `80`.

### Exercise 2

Use `map` to get only student names.

### Exercise 3

Use `find` to get the student named `"Sam"`.

---

## Mini-Task

Filter active users and display names.

```js
const users = [
  { name: "Alex", active: true },
  { name: "Maya", active: false },
  { name: "Sam", active: true },
  { name: "Nina", active: false }
];

const activeUserNames = users
  .filter((user) => user.active)
  .map((user) => user.name);

console.log("Active Users:", activeUserNames);
```

---

## 30-Minute Flow

```text
5 min  → Explain why arrays matter
10 min → Teach forEach, map, filter, find
10 min → Product/student exercises
5 min  → Active users mini-task
```

---

## Expected Outcome

You can use `forEach`, `map`, `filter`, and `find` to work with users, products, and other frontend lists.

---

## Navigation

[← Day 3](day-3) | [Day 5 →](day-5)
