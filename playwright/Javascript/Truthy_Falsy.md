# JavaScript Truthy & Falsy Values (Cheat Sheet)

---

## 1. Falsy Values

Falsy values are values that evaluate to `false` in a boolean context like `if` conditions.


Falsy values are the only 8 values that behave like `false` in JavaScript. They are important for condition checking and control flow. Anything not in this list is considered truthy.

### Falsy List:

* `0`
* `-0`
* `0n` (BigInt zero)
* `NaN`
* `null`
* `undefined`
* `false`
* `""`, `''`, `` (empty strings)

### Example

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
```

---

## 2. Truthy Values

Truthy values are all values that are NOT falsy. They evaluate to `true` in boolean context.

Truthy values include everything not in the falsy list. They are commonly used in condition checks without explicit comparison. Even empty objects and arrays are truthy.

### Examples:

* `{}`
* `[]`
* `true`
* `"0"`
* `"false"`
* `" "`
* `1`, `-1`

### Example

```js
if ({}) console.log("Truthy");
if ([]) console.log("Truthy");
if ("0") console.log("Truthy");
```

---

## 3. Why Truthy / Falsy?

Truthy and falsy values help simplify conditional logic in JavaScript.


They allow writing shorter and cleaner conditions instead of explicit null/undefined checks. This makes code more readable and maintainable. It is widely used in real-world JavaScript applications.

```js
// Instead of this
if (value !== null && value !== undefined) {}

// We write
if (value) {}
```

---

## 4. Logical Operators

### OR (||)

Returns first truthy value.


The OR operator returns the first truthy value it finds. If all values are falsy, it returns the last value. It is commonly used for default values.

```js
console.log(0 || null || "Hello" || 5);
// Hello
```

---

### AND (&&)

Returns first falsy value OR last truthy value.


The AND operator stops at the first falsy value. If all are truthy, it returns the last value. It is used for conditional execution.

```js
console.log("Hi" && 1 && true);
// true

console.log("Hi" && 0 && true);
// 0
```

---

## 5. Nullish Coalescing Operator (??)

Returns right-hand value only if left is `null` or `undefined`.

The nullish coalescing operator provides fallback only for null or undefined values. Unlike ||, it does not treat 0 or empty string as falsy. It is used for precise default handling.

```js
console.log(null ?? "default");
console.log(undefined ?? "fallback");
console.log(0 ?? "fallback");
// 0
```

### Difference from ||

```js
console.log(0 || "fallback");  // fallback
console.log(0 ?? "fallback");  // 0
```

---

## 6. Practice Examples


The double NOT (!!) operator converts values into boolean true or false. It is commonly used to normalize values in JavaScript. It helps quickly check truthy or falsy behavior.

```js
console.log(!!null);       // false
console.log(!!undefined);  // false
console.log(!!0);          // false
console.log(!![]);         // true
```

---

## Quick Summary

* Falsy → 8 values only
* Truthy → everything else
* `||` → first truthy
* `&&` → first falsy / last truthy
* `??` → only null / undefined fallback

---
