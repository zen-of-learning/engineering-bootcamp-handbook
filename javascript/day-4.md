# Day 4 — Arrays

> **Goal:** Use `forEach`, `map`, `filter`, and `find` with real lists of users.

---

## Short Explanation

Frontend apps often receive lists from APIs: users, posts, products, comments, or orders. Array methods help you work with those lists. Use `forEach` when you want to do something for every item. Use `map` when you want to create a new list from an old list. Use `filter` when you want only the items that match a condition. Use `find` when you want the first matching item. Do not worry about deep theory today. Focus on the question each method answers: “do something,” “transform,” “keep some,” or “find one.” These methods are essential before DOM rendering and API work.

---

## Code Examples

```js
const users = [
  { id: 1, name: "Ava", email: "ava@example.com", isActive: true },
  { id: 2, name: "Ben", email: "ben@example.com", isActive: false },
  { id: 3, name: "Cara", email: "cara@example.com", isActive: true }
];
```

Print every name:

```js
users.forEach((user) => {
  console.log(user.name);
});
```

Create a list of emails:

```js
const emails = users.map((user) => {
  return user.email;
});

console.log(emails);
```

Keep only active users:

```js
const activeUsers = users.filter((user) => {
  return user.isActive === true;
});

console.log(activeUsers);
```

Find one user:

```js
const selectedUser = users.find((user) => {
  return user.id === 2;
});

console.log(selectedUser);
```

---

## Exercises

1. Use `forEach` to print every user name.
2. Use `map` to create an array of email addresses.
3. Use `find` to get the user whose name is `"Cara"`.

---

## Mini-Task

Given the `users` array, filter active users and display only their names.

Expected result:

```js
["Ava", "Cara"]
```

Try solving it in two steps:

1. `filter` active users
2. `map` active user names

---

## Expected Outcome

You can work with arrays of objects and choose the right method for common frontend tasks.

---

## Navigation

[← Day 3](day-3) | [Day 5 →](day-5)
