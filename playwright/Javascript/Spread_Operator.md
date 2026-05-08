# TypeScript — Spread Operator (`...`)

The spread operator (`...`) is used to **extract elements from an array** or **properties from an object**.

---

## 1. Logging Array Elements

```typescript
const fruits: string[] = ["apple", "pineapple", "strawberry", "grapes"];

console.log(fruits);    // [ 'apple', 'pineapple', 'strawberry', 'grapes' ]
console.log(...fruits); // apple pineapple strawberry grapes
```

---

## 2. Reference Copy vs. Shallow Copy

### ❌ Reference Copy (both variables point to the same object)

```typescript
const copyFruits = fruits; // Both point to the same array in the heap

copyFruits[1] = "grapes"; // Mutates the original too!

console.log(copyFruits); // [ 'apple', 'grapes', 'strawberry', 'grapes' ]
console.log(fruits);     // [ 'apple', 'grapes', 'strawberry', 'grapes' ] ← also changed!
```

### ✅ Shallow Copy with Spread

```typescript
const fruitsShallowCopy = [...fruits]; // New array with extracted elements

fruitsShallowCopy[0] = "kiwi";
fruitsShallowCopy.push("mango");

console.log(fruitsShallowCopy); // [ 'kiwi', 'grapes', 'strawberry', 'grapes', 'mango' ]
console.log(fruits);            // [ 'apple', 'grapes', 'strawberry', 'grapes' ] ← unchanged
```

---

## 3. Spread on Objects

Spread can merge or extend objects:

```typescript
let person = {
  id: 23,
  name: "John",
  gender: "male",
};

const employee = { ...person, salary: 2000, company: "infa" };

console.log(employee);
// { id: 23, name: 'John', gender: 'male', salary: 2000, company: 'infa' }

console.log(person);
// { id: 23, name: 'John', gender: 'male' } ← unchanged
```

---

## ⚠️ Key Note: Spread is Shallow

The spread operator only works on the **first level**.  
Nested objects or arrays inside an object still share the **same reference**.

```typescript
const original = {
  name: "John",
  address: { city: "NYC" }, // nested object
};

const copy = { ...original };

copy.address.city = "LA"; // ← mutates the original's nested object too!

console.log(original.address.city); // "LA" ← affected!
```

> For a **deep copy**, use `structuredClone()`
