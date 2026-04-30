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
* Immutable and **compared by value**

---

## Non-Primitive Data Types (Reference Types)

* `arrays`
* `objects`
* `functions`

### Memory Behavior

* Actual data is stored in **Heap memory**
* A **reference (address)** to that data is stored in **Stack memory**
* Values are **copied by reference** (multiple variables can point to the same object)
* Compared by **reference**

---

## Key Takeaway

* **Stack →** stores primitive values & references
* **Heap →** stores actual complex data (objects, arrays, functions)

---

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
let notANumber = NaN;
let infinityValue = Infinity;
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

### Primitive Equality Example

```js
let a = 10;
let b = 10;

console.log(a === b); // true
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

### Reference Comparison Example

```js
let obj1 = { name: "Rahul" };
let obj2 = { name: "Rahul" };

console.log(obj1 === obj2); // false
```

---

## Key Note

* Primitive types → stored in **Stack**
* Non-primitive types → stored in **Heap** (reference stored in Stack)
