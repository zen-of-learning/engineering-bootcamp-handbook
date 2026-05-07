# Day 5 — Objects

> **Goal:** Read, update, and organize object data used in real frontend apps.

---

## Short Explanation

Objects describe things. A user object might have a name and email. A product object might have a price and stock count. A settings object might contain nested preferences. Use dot notation when you know the property name. Update a property by assigning a new value. Nested objects help group related details, such as an address inside a user. Arrays of objects are one of the most common frontend data shapes. If you understand them well, API data becomes much easier to handle.

---

## Code Examples

Access and update properties:

```js
const product = {
  name: "Wireless Mouse",
  price: 25,
  inStock: true
};

console.log(product.name);
product.price = 20;
console.log(product.price);
```

Nested object:

```js
const user = {
  name: "Ravi",
  address: {
    city: "Mumbai",
    country: "India"
  }
};

console.log(user.address.city);
```

Array of objects:

```js
const products = [
  { name: "Keyboard", price: 40 },
  { name: "Monitor", price: 180 },
  { name: "USB Cable", price: 8 }
];

products.forEach((product) => {
  console.log(`${product.name}: $${product.price}`);
});
```

---

## Exercises

1. Create a product object and update its price.
2. Create a user object with a nested `address`, then print the city.
3. Loop through an array of products and print each product name.

---

## Mini-Task

Create a product list with at least four products. Each product should have:

- `name`
- `price`
- `category`

Display each product in this format:

```text
Keyboard - $40
Monitor - $180
```

Bonus: filter products cheaper than `$50` and print only those products.

---

## Expected Outcome

You can model real app data with objects, update values, read nested properties, and work with arrays of objects.
---

## Navigation

[← Day 4](day-4) | [Day 6 →](day-6)
