# TypeScript Variables

## What is a Variable?

A variable is a container used to store data.

TypeScript variables are almost similar to JavaScript variables, but TypeScript supports **static typing**.

Static typing helps developers:
- Catch errors early
- Improve code readability
- Get better IntelliSense support in editors

---

# Variable Syntax

```ts
keyword variableName: dataType = value;
```

### Example

```ts
let username: string = "Sri";
let age: number = 25;
let isLoggedIn: boolean = true;
```

---

# Keywords Used for Variables

TypeScript supports 3 keywords:

- `var`
- `let`
- `const`

---

# Data Types

Common primitive data types in TypeScript:

| Data Type | Example |
|---|---|
| string | `"hello"` |
| number | `100` |
| boolean | `true` |

---

# Type Inference

Declaring data types is optional in TypeScript because TS can automatically detect the type.

```ts
let age = 8;
console.log(age);
```

TypeScript automatically infers:

```ts
// age: number
```

---

# Explicit Type Declaration

```ts
let num: number = 20;
console.log(num);
```

---

# var Keyword

`var` is the old way of declaring variables before ES6.

## Features of var

- Can be re-declared
- Can be re-initialized
- Supports hoisting
- Function scoped
- Not recommended in modern TypeScript/JavaScript

---

## Example: var

```ts
var course = "TypeScript";
var course = "JavaScript"; // Re-declaration allowed

console.log(course);
```

---

## Function Scope Example

```ts
function test() {
    var x = 50;

    if (true) {
        var y = 90;

        console.log(x); // 50
        console.log(y); // 90
    }

    // Accessible outside block because var is function scoped
    console.log(y);
}

test();
```

---

# Hoisting with var

Variables declared using `var` are hoisted and initialized with `undefined`.

```ts
console.log(user); // undefined

var user = "Sri";
```

Internally:

```ts
var user;
console.log(user);

user = "Sri";
```

---

# let Keyword

`let` was introduced in ES6 and is recommended for mutable values.

## Features of let

- Cannot be re-declared in same scope
- Can be reassigned
- Block scoped
- Hoisted but stays in Temporal Dead Zone (TDZ)

---

## Example: let

```ts
let city = "Hyderabad";

city = "Bangalore"; // Allowed

console.log(city);
```

---

## Block Scope Example

```ts
function letTest() {
    let x = 5;

    if (true) {
        let y = 2;

        console.log(x); // 5
        console.log(y); // 2
    }

    // Error: y is block scoped
    // console.log(y);
}

letTest();
```

---

# Hoisting with let

```ts
// console.log(emp); // Error

let emp = "Yuvika";
```

Reason:
- `let` variables are hoisted
- But cannot be accessed before declaration
- This phase is called Temporal Dead Zone (TDZ)

---

# const Keyword

`const` is used for constant values.

## Features of const

- Cannot be re-declared
- Cannot be reassigned
- Block scoped
- Best choice for values that should not change

---

## Example: const

```ts
const PI = 3.14;

console.log(PI);

// PI = 5; // Error
```

---

# Real-Time Examples

## User Profile

```ts
const username: string = "john_doe";
let loginCount: number = 10;
let isPremiumUser: boolean = true;

console.log(username);
console.log(loginCount);
console.log(isPremiumUser);
```

---

## E-Commerce Product

```ts
const productName: string = "iPhone 15";
let productPrice: number = 79999;
let inStock: boolean = true;

console.log(productName);
console.log(productPrice);
console.log(inStock);
```

---



# Best Practices

✅ Use `const` by default  
✅ Use `let` when value changes  
❌ Avoid using `var` in modern TypeScript

---

# Summary

- Variables store data
- TypeScript supports static typing
- `let` and `const` are preferred over `var`
- Type inference makes TypeScript smarter
- Block scope improves code safety

---

# Final Example

```ts
const companyName: string = "OpenAI";

let employeeCount: number = 1200;

employeeCount += 100;

console.log(companyName);
console.log(employeeCount);
```