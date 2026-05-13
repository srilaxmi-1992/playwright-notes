# TypeScript Variables — var vs let vs const

TypeScript variables are similar to JavaScript variables, but TypeScript adds **static typing**.

Static typing helps:
- Prevent runtime errors
- Improve IntelliSense
- Make code more readable
- Improve large-scale application development

---

# Variable Syntax

```ts
keyword variableName: dataType = value;
```

## Example

```ts
let username: string = "Sri";
let age: number = 25;
let isActive: boolean = true;
```

---

# Type Inference in TypeScript

TypeScript can automatically detect the datatype.

```ts
let course = "TypeScript";
```

TypeScript infers:

```ts
// course: string
```

---

# 1. var Keyword

`var` is the old variable declaration keyword from ES5.

In modern TypeScript projects, `var` is generally avoided because of scope-related issues.

---

## Features of var

- Function scoped
- Can be re-declared
- Can be reassigned
- Supports hoisting
- Not recommended in modern TS development

---

# TypeScript Example Using var

```ts
var employeeName: string = "Rahul";

employeeName = "Kiran"; // Reassignment allowed

var employeeName: string = "David"; // Re-declaration allowed

console.log(employeeName);
```

---

# Function Scope Example

```ts
function varExample(): void {

    var department: string = "Engineering";

    if (true) {

        var manager: string = "John";

        console.log(department);
        console.log(manager);
    }

    // Accessible outside block
    console.log(manager);
}

varExample();
```

---

# Hoisting with var

```ts
console.log(userName); // undefined

var userName: string = "Sri";
```

Internally:

```ts
var userName: string;

console.log(userName);

userName = "Sri";
```

---

# Problems with var

```ts
for (var i: number = 1; i <= 3; i++) {

    setTimeout(() => {
        console.log(i);
    }, 1000);
}
```

## Output

```ts
4
4
4
```

Reason:
- `var` is function scoped
- Same variable reference is shared

---

# 2. let Keyword

`let` was introduced in ES6 and is recommended for mutable variables.

---

## Features of let

- Block scoped
- Cannot be re-declared in same scope
- Can be reassigned
- Hoisted but exists in TDZ

---

# TypeScript Example Using let

```ts
let studentName: string = "Anu";

studentName = "Keerthi"; // Allowed

console.log(studentName);
```

---

# Block Scope Example

```ts
function letExample(): void {

    let company: string = "Google";

    if (true) {

        let location: string = "Hyderabad";

        console.log(company);
        console.log(location);
    }

    // Error
    // console.log(location);
}

letExample();
```

---

# Hoisting with let

```ts
// console.log(product); // Error

let product: string = "Laptop";
```

Reason:
- `let` variables are hoisted
- But cannot be accessed before declaration
- This is called Temporal Dead Zone (TDZ)

---

# let Solves var Problem

```ts
for (let i: number = 1; i <= 3; i++) {

    setTimeout(() => {
        console.log(i);
    }, 1000);
}
```

## Output

```ts
1
2
3
```

Reason:
- `let` creates separate block-scoped variables

---

# 3. const Keyword

`const` is used for values that should not change.

---

## Features of const

- Block scoped
- Cannot be reassigned
- Cannot be re-declared
- Must initialize during declaration

---

# TypeScript Example Using const

```ts
const companyName: string = "OpenAI";

console.log(companyName);
```

---

# Reassignment Error

```ts
const PI: number = 3.14;

// Error
// PI = 5;
```

---

# const with Objects

Important:
- Object reference cannot change
- But object properties can change

```ts
const user: {
    name: string;
    age: number;
} = {
    name: "Sri",
    age: 25
};

user.age = 26; // Allowed

console.log(user);
```

---

# Real-Time TypeScript Examples

# Employee Management

```ts
const company: string = "Infosys";

let employeeCount: number = 1200;

employeeCount += 50;

console.log(company);
console.log(employeeCount);
```

---

# Banking Application

```ts
let accountBalance: number = 50000;

accountBalance -= 10000;

console.log(accountBalance);
```

---

# E-Commerce Product

```ts
const productId: number = 101;

let stockAvailable: boolean = true;

console.log(productId);
console.log(stockAvailable);
```

---

# var vs let vs const

| Feature | var | let | const |
|---|---|---|---|
| Scope | Function | Block | Block |
| Re-declare | Yes | No | No |
| Reassign | Yes | Yes | No |
| Hoisting | Yes | Yes (TDZ) | Yes (TDZ) |
| Modern Usage | Avoid | Preferred | Most Preferred |

---

# Best Practices in TypeScript

✅ Use `const` by default  
✅ Use `let` when value changes  
❌ Avoid using `var`  

---

# Recommended Modern TS Style

```ts
const appName: string = "Netflix";

let totalUsers: number = 1000000;

totalUsers += 5000;

console.log(appName);
console.log(totalUsers);
```

---

# Summary

- `var` → old, function scoped, avoid
- `let` → mutable values
- `const` → fixed references
- TypeScript adds static typing for better safety
- Modern TS projects mostly use `let` and `const`