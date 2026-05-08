# 📦 JavaScript Spread Operator (...) — Complete Guide

```

**Summary:** The spread operator (...) expands iterable values (arrays, strings, objects) into individual elements or key–value pairs.
---

## 🔢 1. Spread with Arrays

```js
const fruits = ["apple", "pineapple", "strawberry", "grapes"];
console.log(fruits);
console.log(...fruits);   // spreads elements

```

## ✏️ Wrong Copy (Reference Copy)

```js
const copyFruits = fruits;   // both variables point to SAME array
copyFruits[1] = "grapes";

console.log(copyFruits);
console.log(fruits);         // original also changes

```


---

## 📏 Correct Shallow Copy

```js
const fruitsShallowCopy = [...fruits];

fruitsShallowCopy[0] = "kiwi";
fruitsShallowCopy.push("mango");

console.log(fruitsShallowCopy); // modified copy
console.log(fruits);            // original unchanged

```


## 2. Spread with Objects

### End

```js
let person = {
    id: 23,
    name: "John",
    gender: "male"
};

const employee = { ...person, salary: 2000, company: "infa" };

console.log(employee);
console.log(person);

```

✔️ employee gets all properties of person plus new ones
✔️ person remains unchanged

### 3. Important Note — Spread is Shallow, Not Deep

Spread copies only the first level.

```js
const user = {
    name: "Alice",
    address: {
        city: "Miami",
        zip: 44123
    }
};

const userCopy = { ...user };

userCopy.address.city = "Orlando";

console.log(userCopy.address.city);  // Orlando
console.log(user.address.city);      // Orlando ❌ also changed!

```


---

## 4. How to Make a Deep Copy (Correct Way)

### End

```js
const deepCopy = structuredClone(user);

```

**Summary:** Removes last item.

### Start

```js
const deepCopy = {
    ...user,
    address: { ...user.address }
};

```

## 🧠 Key Takeaways

Spread operator expands arrays/objects.

Spread creates shallow copies, not deep copies.

Nested objects/arrays still reference the same memory.

Use structuredClone() or manual copying for deep clones.

---
