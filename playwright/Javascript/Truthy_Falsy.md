# JavaScript Truthy & Falsy Values

## 1. Falsy Values

Falsy values are values that convert to `false` when used in a boolean context (like in `if` conditions).

**List of all falsy values in JavaScript:**

* `0`
* `-0`
* `0n` (BigInt zero)
* `NaN`
* `null`
* `undefined`
* `false`
* `""`, `''`, ```` (empty strings)

### Example:

```js
if (0) {
  console.log("Truthy");
} else {
  console.log("Falsy"); // Output
}

if ("") {
  console.log("Truthy");
} else {
  console.log("Falsy"); // Output
}

if (null) {
  console.log("Truthy");
} else {
  console.log("Falsy"); // Output
}
```

---

## 2. Truthy Values

Truthy values are all values **except falsy values**. They evaluate to `true` in a boolean context.

**Examples of truthy values:**

* `{}` (empty object)
* `[]` (empty array)
* `true`
* `"0"` (string, not number)
* `"false"` (string)
* `" "` (space inside string)
* `1`, `-1` (non-zero numbers)

### Example:

```js
if ({}) {
  console.log("Truthy"); // Output
}

if ([]) {
  console.log("Truthy"); // Output
}

if ("0") {
  console.log("Truthy"); // Output
}
```

---

## 3. Why Do We Use Truthy & Falsy?

JavaScript uses truthy/falsy values to simplify conditions without strict comparisons.

Instead of:

```js
if (value !== null && value !== undefined && value !== false)
```

We can simply write:

```js
if (value) {
  console.log("Value exists");
}
```

This makes code shorter and cleaner.

---

## 4. Logical Operators (|| and &&)

### OR (`||`) Operator

* Returns the **first truthy value**
* If all are falsy, returns the **last value**

```js
console.log(0 || null || "Hello" || 5); 
// Output: "Hello"

console.log(null || undefined || 0); 
// Output: 0
```

---

### AND (`&&`) Operator

* Returns the **first falsy value**
* If all are truthy, returns the **last value**

```js
console.log("Hi" && 1 && true); 
// Output: true

console.log("Hi" && 0 && true); 
// Output: 0
```

---

## 5. Practice with if Conditions

```js
let value = " ";

if (value) {
  console.log("Truthy value");
} else {
  console.log("Falsy value");
}
// Output: Truthy value


let value2 = NaN;

if (value2) {
  console.log("Truthy value");
} else {
  console.log("Falsy value");
}
// Output: Falsy value
```

---

## Quick Summary

* Falsy = behaves like `false` (only 8 values)
* Truthy = everything else
* `||` → first truthy
* `&&` → first falsy OR last truthy
* Used to write clean and short conditions

---
