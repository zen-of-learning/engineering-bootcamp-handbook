# Day 2 — Arrays and Objects Basics

## Goal

Students should learn how to group data using arrays and objects.

---

## Practical Explanation

Frontend apps rarely work with single values only.

Instead of this:

```js
const hobby1 = "coding";
const hobby2 = "gaming";
const hobby3 = "music";
```

Use an array:

```js
const hobbies = ["coding", "gaming", "music"];
```

Instead of this:

```js
const name = "Alex";
const age = 22;
const city = "Dallas";
```

Use an object:

```js
const user = {
  name: "Alex",
  age: 22,
  city: "Dallas"
};
```

Arrays are good for lists.  
Objects are good for describing one thing.

---

## Arrays

An array stores multiple values.

```js
const colors = ["red", "blue", "green"];

console.log(colors);
```

Access items by index.

```js
console.log(colors[0]); // red
console.log(colors[1]); // blue
console.log(colors[2]); // green
```

Indexes start at `0`.

---

## Adding Items to an Array

```js
const hobbies = ["coding", "music"];

hobbies.push("football");

console.log(hobbies);
```

Result:

```js
["coding", "music", "football"]
```

---

## Array Length

```js
const users = ["Alex", "Maya", "Sam"];

console.log(users.length); // 3
```

---

## Objects

Objects store related information.

```js
const user = {
  name: "Maya",
  age: 25,
  email: "maya@example.com",
  isActive: true
};
```

Access object properties:

```js
console.log(user.name);
console.log(user.email);
```

---

## Updating Object Properties

```js
const user = {
  name: "Maya",
  age: 25
};

user.age = 26;

console.log(user);
```

---

## Array of Objects

This is one of the most important patterns in frontend development.

```js
const users = [
  {
    name: "Alex",
    age: 22
  },
  {
    name: "Maya",
    age: 25
  },
  {
    name: "Sam",
    age: 20
  }
];

console.log(users[0].name);
console.log(users[1].age);
```

Most API data looks like this.

---

## Guided Example

Create a small user list.

```js
const users = [
  {
    name: "Alex",
    age: 22,
    city: "Dallas"
  },
  {
    name: "Maya",
    age: 25,
    city: "Austin"
  },
  {
    name: "Sam",
    age: 20,
    city: "Houston"
  }
];

console.log(users[0]);
console.log(users[0].name);
console.log(users[1].city);
```

---

## Common Mistakes

### Mistake 1: Forgetting commas

Wrong:

```js
const user = {
  name: "Alex"
  age: 22
};
```

Correct:

```js
const user = {
  name: "Alex",
  age: 22
};
```

### Mistake 2: Accessing wrong index

```js
const names = ["Alex", "Maya"];

console.log(names[2]); // undefined
```

There is no third item.

### Mistake 3: Confusing array and object

Array:

```js
const users = ["Alex", "Maya"];
```

Object:

```js
const user = {
  name: "Alex",
  age: 22
};
```

---

## Exercises

### Exercise 1

Create an array called `favoriteFoods`.

Add 4 foods.

Print:

- First food
- Last food
- Total number of foods

### Exercise 2

Create a student object with:

- `name`
- `age`
- `grade`
- `isEnrolled`

Print a sentence using those values.

### Exercise 3

Create an array of 3 products.

Each product should have:

- `name`
- `price`
- `inStock`

Print the first product name and price.

---

## Mini-Task

Create user data.

```js
const user = {
  name: "John",
  age: 28,
  hobbies: ["traveling", "fitness", "movies"],
  address: {
    city: "Dallas",
    state: "TX"
  }
};

console.log(`${user.name} is ${user.age} years old.`);
console.log("First hobby:", user.hobbies[0]);
console.log("City:", user.address.city);
```

---

## 30-Minute Flow

```text
5 min  → Explain arrays vs objects
10 min → Guided user/product examples
10 min → Exercises
5 min  → Mini-task review
```

---

## Expected Outcome

You can group values in arrays, describe one item with an object, update object properties, and read nested user data.

---

## Navigation

[← Day 1](day-1) | [Day 3 →](day-3)
