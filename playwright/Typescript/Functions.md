# TypeScript Functions

## Introduction

Functions in TypeScript are reusable blocks of code used to perform specific tasks. TypeScript adds **types** to functions, making code safer and easier to maintain.

---

# 1. Simple Function in TypeScript

## Summary

A simple function contains:

* Function name
* Parameters
* Return type
* Function body

## Syntax

```ts
function functionName(parameter: type): returnType {
    // code
}
```

## Example

```ts
function greet(name: string): string {
    return `Hello, ${name}`;
}

console.log(greet("John"));
```

## Explanation

* `name: string` → parameter type
* `: string` after parentheses → return type
* Function returns a string value

---

# 2. Arrow Functions

## Summary

Arrow functions provide a shorter syntax for writing functions.

## Syntax

```ts
const functionName = (parameter: type): returnType => {
    // code
};
```

## Example

```ts
const add = (a: number, b: number): number => {
    return a + b;
};

console.log(add(10, 20));
```

## Explanation

* Uses `=>` arrow syntax
* Commonly used in modern TypeScript and JavaScript
* Cleaner and shorter syntax

---

# 3. Function Expressions

## Summary

A function expression stores a function inside a variable.

## Syntax

```ts
const variableName = function(parameter: type): returnType {
    // code
};
```

## Example

```ts
const multiply = function(a: number, b: number): number {
    return a * b;
};

console.log(multiply(4, 5));
```

## Explanation

* Function is assigned to a variable
* Useful for callbacks and dynamic functions

---

# 4. Default Parameters

## Summary

Default parameters allow assigning default values to function parameters.

## Syntax

```ts
function functionName(parameter: type = defaultValue): returnType {
    // code
}
```

## Example

```ts
function welcome(name: string = "Guest"): string {
    return `Welcome, ${name}`;
}

console.log(welcome());
console.log(welcome("Alice"));
```

## Explanation

* If no argument is passed, default value is used
* Makes parameters optional automatically

---

# 5. Optional Parameters

## Summary

Optional parameters are parameters that may or may not be provided.

## Syntax

```ts
function functionName(parameter?: type): returnType {
    // code
}
```

## Example

```ts
function displayMessage(message?: string): void {
    console.log(message || "No message provided");
}

displayMessage("Hello");
displayMessage();
```

## Explanation

* `?` makes parameter optional
* Optional parameters should usually come last

---

# 6. Rest Parameters (Multiple Parameters)

## Summary

Rest parameters allow a function to accept multiple values as an array.

## Syntax

```ts
function functionName(...parameter: type[]): returnType {
    // code
}
```

## Example

```ts
function total(...numbers: number[]): number {
    return numbers.reduce((sum, num) => sum + num, 0);
}

console.log(total(1, 2, 3, 4, 5));
```

## Explanation

* `...` is called the rest operator
* Stores multiple values in an array
* Useful when number of arguments is unknown

---

# 7. Function Overloading in TypeScript

## Summary

Function overloading allows multiple function signatures for the same function.

## Syntax

```ts
function functionName(param: type): returnType;
function functionName(param1: type, param2: type): returnType;

function functionName(param1: any, param2?: any): any {
    // implementation
}
```

## Example

```ts
function combine(a: string, b: string): string;
function combine(a: number, b: number): number;

function combine(a: any, b: any): any {
    return a + b;
}

console.log(combine("Hello ", "World"));
console.log(combine(10, 20));
```

## Explanation

* Multiple function signatures are declared
* Only one implementation is written
* TypeScript chooses the correct overload automatically

---

# Complete Example Using All Concepts

```ts
// Simple Function
function square(num: number): number {
    return num * num;
}

// Arrow Function
const subtract = (a: number, b: number): number => a - b;

// Function Expression
const divide = function(a: number, b: number): number {
    return a / b;
};

// Default Parameter
function greetUser(name: string = "Guest"): string {
    return `Hello ${name}`;
}

// Optional Parameter
function printAge(age?: number): void {
    console.log(age || "Age not provided");
}

// Rest Parameter
function sumAll(...nums: number[]): number {
    return nums.reduce((total, n) => total + n, 0);
}

// Function Overloading
function format(value: string): string;
function format(value: number): string;

function format(value: any): string {
    return `Formatted Value: ${value}`;
}

console.log(square(5));
console.log(subtract(10, 5));
console.log(divide(20, 4));
console.log(greetUser());
printAge();
console.log(sumAll(1, 2, 3, 4));
console.log(format("TypeScript"));
```

---

# Final Summary

| Concept              | Purpose                      |
| -------------------- | ---------------------------- |
| Simple Function      | Basic reusable code block    |
| Arrow Function       | Short modern syntax          |
| Function Expression  | Store function in variable   |
| Default Parameters   | Set default values           |
| Optional Parameters  | Parameters not required      |
| Rest Parameters      | Accept multiple arguments    |
| Function Overloading | Multiple function signatures |

---

# Conclusion

Functions are one of the most important parts of TypeScript. TypeScript improves functions by adding:

* Type safety
* Better readability
* Better development experience
* Error prevention

Understanding these function concepts helps in writing clean and scalable TypeScript applications.
