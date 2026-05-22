# Type Inference in TypeScript

## What is Type Inference?

Type Inference means if you do not explicitly specify a datatype, TypeScript automatically identifies and assigns the datatype based on the assigned value.

TypeScript implicitly infers the type during compilation.

---

# Example

```ts
export { }

// Type Inference
// TypeScript automatically assigns datatype based on value

let user = "yuvika"
// inferred as string

let age = 20
// inferred as number

let flag = false
// inferred as boolean
```

---

# Real-Time Examples

## Example 1 - User Information

```ts
let username = "Naresh"
// string

let loginCount = 10
// number

let isLoggedIn = true
// boolean
```

TypeScript automatically infers:

```ts
username: string
loginCount: number
isLoggedIn: boolean
```

---

# Arrays Type Inference

```ts
let colors = ["red", "blue"]
// string[]

let nums = [1, 2, 3]
// number[]

let vals = [false, true, false, true]
// boolean[]
```

TypeScript infers array types automatically.

---

# Object Type Inference

```ts
let emp = {
    name: "naresh",
    age: 38,
    isWorking: true,
    salary: 250000.00
}
```

TypeScript infers:

```ts
{
   name: string,
   age: number,
   isWorking: boolean,
   salary: number
}
```

---

# Real-Time Employee Example

```ts
let employee = {
    empId: 101,
    empName: "John",
    department: "QA",
    isPermanent: true
}
```

Automatically inferred as:

```ts
{
   empId: number,
   empName: string,
   department: string,
   isPermanent: boolean
}
```

---

# Function Return Type Inference

```ts
function add(a: number, b: number) {
    return a + b
}
```

TypeScript automatically infers return type as:

```ts
number
```

---

# Type Inference Advantage

- Less code
- Cleaner syntax
- Better readability
- Auto IntelliSense support
- Compile-time type safety

---

# Important Note

Once TypeScript infers a datatype, you cannot assign another datatype later.

```ts
let city = "Hyderabad"

city = "Chennai" // valid

city = 100
// Error because city is inferred as string
```

---

# Explicit Typing vs Type Inference

## Explicit Typing

```ts
let name: string = "Naresh"
```

## Type Inference

```ts
let name = "Naresh"
```

Both are valid.

---

# Best Practice

Use Type Inference when datatype is obvious.

Use Explicit Typing:
- in functions
- APIs
- reusable components
- complex objects
- interfaces

---

# Summary

| Value     | Inferred Type |
|---        |---            |
| `"hello"` | string        |
| `100`     | number        |
| `true`    | boolean       |
| `[1,2,3]` | number[]      |
| `["a","b"]` | string[]    |
| `{name:"john"}` | object  |
