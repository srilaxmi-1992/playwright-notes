# 📘 JavaScript Functions

A well-organized reference for understanding core JavaScript function concepts.

---

## 🔹 1. Named Function Declaration

A function defined using the `function` keyword with a name.

```js
function greet() {
    console.log("Hello Srilaxmi");
}

greet();
```

**Summary:**
Named functions are **hoisted**, meaning they can be called before they are defined. They are best suited for reusable logic across your program.

---

## 🔹 2. Function with Parameters

Functions can accept inputs (parameters) to make them dynamic.

```js
function add(a, b) {
    console.log("Add: " + (a + b));
}

add(26, 99); // arguments
```

**Summary:**

* `a`, `b` → parameters
* `26`, `99` → arguments
  Parameters are **local variables** inside the function.

---

## 🔹 3. Function with Return Value

Functions can return values using the `return` keyword.

```js
function square(a) {
    return a * a;
}

console.log(square(5));
```

**Summary:**
Returning values makes functions **reusable and composable**, instead of just printing output.

---

## 🔹 4. Function Expression

A function stored inside a variable.

```js
let subtract = function (a, b) {
    console.log("Subtraction: " + (a - b));
};

subtract(9, 6);
```

**Summary:**

* Not hoisted like declarations
* Useful for dynamic behavior and passing functions around

---

## 🔹 5. Arrow Functions (ES6)

Shorter syntax for writing functions.

```js
let multiply = (a, b) => {
    console.log("Multiply: " + (a * b));
};

multiply(9, 9);
```

**Summary:**

* Cleaner and shorter syntax
* Does **not have its own `this`**
* Best for small, simple logic

---

## 🔹 6. Function with Default Parameters

Default values prevent `undefined` issues.

```js
function addition(num1, num2, num3) {
    console.log(num1 + num2 + num3);
}

addition(5, 6); // NaN (num3 is undefined)
```

```js
function addition1(num1, num2, num3 = 9) {
    console.log(num1 + num2 + num3);
}

addition1(5, 6);     // 20
addition1(5, 6, 1);  // 12
```

**Summary:**
Default parameters ensure functions work even when some arguments are missing.

# Short Arrow Function

## Code

```js
const add = (a, b) => a + b;

console.log(add(10, 5));
```

---

## Output

```text
15
```

---

## Summary

- Arrow functions provide a shorter syntax for writing functions.  
- If there is only one expression, the return is implicit (no need for `return`).  
- Commonly used for cleaner and more readable code.

---

# IIFE (Immediately Invoked Function Expression)

## 📌 Definition

An **IIFE** is a JavaScript function that is executed immediately after it is defined.

---

## 🧾 Syntax

```js
(function () {
  console.log("IIFE function");
})();
```

---

## ⚙️ How It Works

* `function () { ... }` → defines a function
* Wrapping in `( )` → converts it into an **expression**
* Final `()` → **immediately invokes** the function

---

## 🎯 Why Use IIFE?

* ✅ Prevents global scope pollution
* ✅ Creates private variables (data hiding)
* ✅ Executes code immediately
* ✅ Useful for initialization logic

---

## 🔄 Variations

### 1. Anonymous IIFE

```js
(function () {
  console.log("Anonymous IIFE");
})();
```

### 2. Named IIFE

```js
(function iife() {
  console.log("Named IIFE");
})();
```

### 3. Arrow Function IIFE

```js
(() => {
  console.log("Arrow IIFE");
})();
```

### 4. IIFE with Parameters

```js
(function (name) {
  console.log("Hello " + name);
})("John");
```

---

## 📦 Example (Private Scope)

```js
const counter = (function () {
  let count = 0;

  return {
    increment: function () {
      count++;
      return count;
    }
  };
})();

console.log(counter.increment()); // 1
console.log(counter.increment()); // 2
```

👉 `count` is private and cannot be accessed directly.

---

## 🧠 Summary

* IIFE = Function that runs immediately
* Helps avoid global variables
* Creates isolated scope
* Common before ES6 modules



## 🔹 7. Key Notes (Best Practices)

* ✅ Use **meaningful function names**
* ✅ Prefer `return` over `console.log()` for reusable logic
* ✅ Handle **missing arguments carefully**
* ✅ Use arrow functions for **short operations**
* ❗ Avoid overusing arrow functions when `this` is required

---

## 🧠 Final Takeaways

* Functions are **reusable building blocks** of JavaScript
* Multiple function styles exist for different use cases
* Understanding **parameters, return values, and defaults** is essential
* Writing clean and structured functions improves maintainability

---

## 📌 Quick Comparison Table

| Feature         | Named Function | Function Expression | Arrow Function |
| --------------- | -------------- | ------------------- | -------------- |
| Hoisted         | ✅ Yes          | ❌ No                | ❌ No           |
| Syntax          | Standard       | Flexible            | Short          |
| `this` behavior | Own            | Own                 | Inherited      |
| Best Use Case   | Reusable code  | Dynamic usage       | Short logic    |

---
