# JavaScript Data Types & Memory Management

## Primitive Data Types

* `string`
* `number`
* `boolean`
* `null`
* `undefined`
* `bigint`
* `symbol`

### Memory Behavior

* Stored directly in **Stack memory**
* Values are **copied by value** (independent copies)

---

## Non-Primitive Data Types (Reference Types)

* `arrays`
* `objects`
* `functions`

### Memory Behavior

* Actual data is stored in **Heap memory**
* A **reference (address)** to that data is stored in **Stack memory**
* Values are **copied by reference** (multiple variables can point to same object)

---

## Key Takeaway

* **Stack → stores primitive values & references**
* **Heap → stores actual complex data (objects, arrays, functions)**

# JavaScript Data Types – Declarations & Examples

## Primitive Data Types

### String

```js
let name = "Chris Evans";
let greeting = 'Hello';
let message = `Hi, ${name}`;
```

### Number

```js
let age = 30;
let price = 99.99;
NaN, infinity
```

### Boolean

```js
let isActive = true;
let isLoggedIn = false;
```

### Null

```js
let data = null;
```

### Undefined

```js
let value;
console.log(value); // undefined
```

### BigInt

```js
let bigNumber = 123456789012345678901234567890n;
```

### Symbol

```js
let id = Symbol("uniqueId");
```

---

## Non-Primitive Data Types (Reference Types)

### Array

```js
let numbers = [1, 2, 3, 4];
let names = ["A", "B", "C"];
```

### Object

```js
let user = {
  name: "Srilaxmi",
  age: 30,
  isActive: true
};
```

### Function

```js
function greet() {
  console.log("Hello!");
}

// Arrow function
const add = (a, b) => a + b;
```

---

## Key Note

* Primitive types → stored in **Stack**
* Non-primitive types → stored in **Heap (reference in Stack)**

