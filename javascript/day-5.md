# Day 5 — Objects, Nested Objects, Array of Objects

## Goal

Students should learn how real-world frontend data is structured.

---

## Practical Explanation

Most frontend data is object-based.

A user is an object.

```js
const user = {
  name: "Alex",
  email: "alex@example.com"
};
```

A product is an object.

```js
const product = {
  name: "Laptop",
  price: 1200
};
```

A list of products is an array of objects.

```js
const products = [
  { name: "Laptop", price: 1200 },
  { name: "Mouse", price: 25 }
];
```

This is exactly how API data often looks.

---

## Accessing Object Properties

```js
const product = {
  name: "Laptop",
  price: 1200,
  inStock: true
};

console.log(product.name);
console.log(product.price);
console.log(product.inStock);
```

Alternative syntax:

```js
console.log(product["name"]);
```

Most of the time, use dot syntax:

```js
product.name
```

---

## Updating Object Properties

```js
const product = {
  name: "Laptop",
  price: 1200
};

product.price = 999;

console.log(product);
```

---

## Adding New Properties

```js
const user = {
  name: "Alex"
};

user.email = "alex@example.com";

console.log(user);
```

---

## Nested Objects

Objects can contain other objects.

```js
const user = {
  name: "Maya",
  address: {
    city: "Dallas",
    state: "TX"
  }
};

console.log(user.address.city);
```

---

## Arrays Inside Objects

```js
const user = {
  name: "Sam",
  skills: ["HTML", "CSS", "JavaScript"]
};

console.log(user.skills[0]);
```

---

## Array of Objects

```js
const products = [
  {
    id: 1,
    name: "Laptop",
    price: 1200,
    inStock: true
  },
  {
    id: 2,
    name: "Mouse",
    price: 25,
    inStock: true
  },
  {
    id: 3,
    name: "Monitor",
    price: 250,
    inStock: false
  }
];
```

Display product names and prices:

```js
products.forEach((product) => {
  console.log(`${product.name} - $${product.price}`);
});
```

Filter available products:

```js
const availableProducts = products.filter((product) => product.inStock);

console.log(availableProducts);
```

---

## Guided Example

Create a product catalog.

```js
const products = [
  {
    id: 1,
    name: "Laptop",
    price: 1200,
    category: "Electronics",
    rating: 4.8
  },
  {
    id: 2,
    name: "Headphones",
    price: 150,
    category: "Electronics",
    rating: 4.5
  },
  {
    id: 3,
    name: "Coffee Mug",
    price: 12,
    category: "Kitchen",
    rating: 4.2
  }
];

products.forEach((product) => {
  console.log(`${product.name} costs $${product.price}`);
});
```

---

## Common Mistakes

### Mistake 1: Forgetting nested access

Wrong:

```js
console.log(user.city);
```

Correct:

```js
console.log(user.address.city);
```

### Mistake 2: Treating an object like an array

Wrong:

```js
console.log(user[0]);
```

Correct:

```js
console.log(user.name);
```

### Mistake 3: Treating an array like an object

Wrong:

```js
console.log(products.name);
```

Correct:

```js
console.log(products[0].name);
```

---

## Exercises

### Exercise 1

Create a movie object with:

- `title`
- `year`
- `rating`
- `genres`

Print the title and first genre.

### Exercise 2

Create a user object with nested address:

- `name`
- `email`
- `address.city`
- `address.state`

Print the city.

### Exercise 3

Create an array of 3 products.

Each product should have:

- `name`
- `price`
- `inStock`

Print only products that are in stock.

---

## Mini-Task

Create a product list and display product names plus prices.

```js
const products = [
  { name: "Laptop", price: 1200, inStock: true },
  { name: "Phone", price: 800, inStock: true },
  { name: "Tablet", price: 400, inStock: false }
];

products.forEach((product) => {
  const stockStatus = product.inStock ? "Available" : "Out of Stock";

  console.log(`${product.name}: $${product.price} - ${stockStatus}`);
});
```

This introduces the ternary operator naturally, but do not go deep yet.

---

## Expected Outcome

You can read and update object data, work with nested objects, read arrays inside objects, and display product data from an array of objects.

---

## Navigation

[← Day 4](day-4) | [Day 6 →](day-6)
