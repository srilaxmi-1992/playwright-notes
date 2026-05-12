# TypeScript Introduction

## What is TypeScript?

TypeScript (TS) is an open-source programming language developed by Microsoft.

TypeScript is a **superset of JavaScript**, which means:

> All JavaScript code can run in TypeScript.

TypeScript adds additional features on top of JavaScript such as:

- Static typing
- Interfaces
- Type safety
- Better tooling support
- Improved developer experience

TypeScript code is converted into JavaScript before running in the browser or Node.js.

---

## Why TypeScript?

JavaScript is powerful, but in large applications it can become difficult to manage and debug.

TypeScript solves many common problems by adding type checking and development tools.

### Benefits of TypeScript

- Detects errors during development
- Makes code easier to understand
- Improves code maintainability
- Better auto-completion and IntelliSense
- Easier teamwork in large projects
- Supports modern JavaScript features

### Example

### JavaScript

```js
function add(a, b) {
  return a + b;
}

add(10, "20"); // No error
```

### TypeScript

```ts
function add(a: number, b: number): number {
  return a + b;
}

add(10, "20"); // Error
```

TypeScript catches the error before running the code.

---

# TypeScript vs JavaScript

| Feature                    | JavaScript                  | TypeScript |
|---                         |---                          |---         | 
| Typing                     | Dynamic                     | Static |
| Compilation                | No compilation needed       | Compiles to JavaScript |
| Error Checking             | Runtime                     | Compile time |
| Tooling Support            | Basic                       | Advanced |
| Code Maintainability       | Harder in large apps        | Easier |
| Learning Curve             | Easier                      | Slightly higher |

### Important Point

> TypeScript is a superset of JavaScript.  
> All JavaScript code can run in TypeScript.

---

# Installing TypeScript

Before installing TypeScript, make sure Node.js is installed.

Check versions:

```bash
node -v
npm -v
```

## Install TypeScript Globally

```bash
npm install -g typescript
```

Verify installation:

```bash
tsc -v
```

---

# Compiling TypeScript

TypeScript files use the `.ts` extension.

Example:

```ts
// app.ts

let message: string = "Hello TypeScript";

console.log(message);
```

Compile the file:

```bash
tsc app.ts
```

After compilation:

```bash
app.js
```

is generated automatically.

Run the JavaScript file:

```bash
node app.js
```

---
# Running TypeScript Files

Normally TypeScript files are compiled first and then executed.

---

## Method 1: Compile and Run

Compile the TypeScript file:

```bash
tsc app.ts
```

This generates:

```bash
app.js
```

Run the generated JavaScript file:

```bash
node app.js
```

---

## Method 2: Run Directly Using TypeScript Executor

You can execute TypeScript files directly without manually compiling them.

Install TypeScript Executor globally:

```bash
npm install -g tsx
```

Run the TypeScript file:

```bash
tsx app.ts
```

### Benefits of Using tsx

- No manual compilation required
- Faster development workflow
- Simple execution process
- Modern TypeScript support
- Works well with Node.js projects

---

# Example

## app.ts

```ts
let username: string = "John";

console.log(username);
```

Run directly:

```bash
tsx app.ts
```

Output:

```bash
John
```

---

# Final Note

Using `tsx` is one of the easiest ways to run TypeScript files directly during development.

---

# Summary

- TypeScript is a superset of JavaScript
- All JavaScript code can run in TypeScript
- TypeScript provides static typing
- TypeScript improves code quality and maintainability
- `.ts` files are compiled into JavaScript

---

# Final Note

JavaScript gives flexibility, while TypeScript provides safety and structure.

For small projects JavaScript works well, but for large-scale applications TypeScript is highly recommended.