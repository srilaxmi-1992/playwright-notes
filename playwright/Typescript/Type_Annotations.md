# Type Annotations
---

## What is Type Annotation?

Type Annotation means explicitly defining the datatype of a variable, parameter, function return type, object property, array, or class member.

It helps:
- Prevent runtime errors
- Improve code readability
- Enable better IntelliSense and auto-completion
- Improve maintainability in large projects
- Catch bugs during development itself

---

# 📌 Syntax of Type Annotation

```typescript
let variableName: datatype = value;
```

Example:

```typescript
let username: string = "Naresh";
let age: number = 30;
let isActive: boolean = true;
```

Here:
- `:` → used for annotation
- `string`, `number`, `boolean` → datatypes

---

# 📌 Why Type Annotations are Important?

## Benefits

| Benefit               | Description                                   |
|---                    |---                                            |
| Error Prevention      | Detects datatype mistakes during development  |
| Better Readability    | Developers easily understand variable types   |
| IntelliSense Support  | Better suggestions in VS Code                 |
| Code Maintenance      | Easier to maintain large projects             |
| Refactoring Safety    | Safer code updates                            |

---

# 📌 Primitive Data Types in TypeScript

Primitive types store a single value.

## 1. String

```typescript
let user: string = "Yuvika";
```

Used for:
- Names
- Emails
- URLs
- Messages

---

## 2. Number

```typescript
let age: number = 20;
let salary: number = 250000.50;
```

Used for:
- Age
- Salary
- Product Price
- Test Data IDs

---

## 3. Boolean

```typescript
let flag: boolean = false;
```

Used for:
- Login status
- Feature toggle
- API success/failure

---

## 4. Undefined

```typescript
let data: undefined = undefined;
```

Represents:
- Variable declared but not assigned

---

## 5. Null

```typescript
let value: null = null;
```

Represents:
- Intentional empty value

---

## 6. Any

```typescript
let response: any = "Hello";
response = 100;
response = true;
```

Used when:
- Type is unknown
- Dynamic API responses

⚠️ Avoid excessive usage of `any` because it removes TypeScript safety.

---

## 7. Void

Used mainly in functions that do not return anything.

```typescript
function printMessage(): void {
    console.log("Hello");
}
```

---

## 8. Union Type

Allows multiple datatypes.

```typescript
let id: string | number;

id = 101;
id = "EMP101";
```

Real-time use:
- API response IDs
- Dynamic form inputs

---

# 📌 Variable Declaration with Type Annotation

```typescript
export {}

let user: string = "yuvika";
let age: number = 20;
let flag: boolean = false;
```

Explanation:
- `user` → accepts only string
- `age` → accepts only number
- `flag` → accepts only boolean

---

# 📌 Non-Primitive Data Types

Non-primitive types can store multiple values or complex structures.

## Examples:
- Arrays
- Objects
- Functions
- Classes
- Interfaces
- Tuples

---

# 📌 Arrays in TypeScript

## String Array

```typescript
let colors: string[] = ["red", "blue"];
```

## Number Array

```typescript
let nums: number[] = [1, 2, 3];
```

## Boolean Array

```typescript
let vals: boolean[] = [false, true, false, true];
```

---

# 📌 Real-Time Array Example (Automation Testing)

```typescript
let browserNames: string[] = ["Chrome", "Firefox", "Edge"];

for(let browser of browserNames){
    console.log(browser);
}
```

Used in:
- Cross-browser testing
- Test configuration setup

---

# 📌 Object Type Annotation

Objects contain multiple properties.

## Example

```typescript
let emp: {
    name: string;
    age: number;
    isWorking: boolean;
    salary: number;
} = {
    name: "naresh",
    age: 38,
    isWorking: true,
    salary: 250000.00
}
```

---

# 📌 Accessing Object Data

```typescript
console.log(emp.name);
console.log(emp.salary);
```

---

# 📌 Looping Object Entries

```typescript
for(let [key, value] of Object.entries(emp)){

    console.log(key, value)
}
```

Output:

```text
name naresh
age 38
isWorking true
salary 250000
```

---

# 📌 Real-Time Employee Management Example

```typescript
type Employee = {
    id: number;
    name: string;
    department: string;
    isActive: boolean;
}

let employee: Employee = {
    id: 101,
    name: "John",
    department: "QA Automation",
    isActive: true
}

console.log(employee);
```
---

# 📌 Function Type Annotation

Functions can also have annotations.

## Example

```typescript
function add(a: number, b: number): number {
    return a + b;
}

console.log(add(10, 20));
```

Explanation:
- `a:number` → parameter type
- `b:number` → parameter type
- `:number` → return type

---

# 📌 Real-Time API Validation Example

```typescript
function validateStatus(statusCode: number): boolean {

    if(statusCode === 200){
        return true;
    }

    return false;
}

console.log(validateStatus(200));
```

Used in:
- API automation testing
- Backend validations

---

# 📌 Tuple Type

Tuple stores fixed datatype values in order.

```typescript
let employeeData: [number, string, boolean];

employeeData = [101, "Naresh", true];
```

Used in:
- Database records
- API response mapping

---

# 📌 Interface Example

Interfaces define object structure.

```typescript
interface User {

    id: number;
    username: string;
    isAdmin: boolean;
}

let user1: User = {

    id: 1,
    username: "admin",
    isAdmin: true
}
```

---

# 📌 Real-Time Selenium Playwright Example

```typescript
interface LoginData {

    username: string;
    password: string;
}

const login: LoginData = {

    username: "admin@test.com",
    password: "admin123"
}

console.log(login);
```

Used in:
- Test automation frameworks
- Data-driven testing

---

# 📌 Type Inference vs Type Annotation

## Type Inference

TypeScript automatically detects datatype.

```typescript
let city = "Hyderabad";
```

TypeScript infers:
```typescript
string
```

---

## Explicit Type Annotation

```typescript
let city: string = "Hyderabad";
```

---

# 📌 When to Use Type Annotations?

## Recommended Usage

| Scenario | Use Annotation? |
|---|---|
| API responses | ✅ Yes |
| Function parameters | ✅ Yes |
| Function return types | ✅ Yes |
| Complex objects | ✅ Yes |
| Arrays | ✅ Yes |
| Simple local variables | Optional |

---

# 📌 Best Practices

## ✅ Use explicit types for functions

```typescript
function multiply(a: number, b: number): number {
    return a * b;
}
```

---

## ✅ Avoid excessive use of `any`

❌ Bad:

```typescript
let data: any = "hello";
```

✅ Better:

```typescript
let data: string = "hello";
```

---

## ✅ Use interfaces for reusable objects

```typescript
interface Product {

    id: number;
    name: string;
    price: number;
}
```

---

# 📌 Common Errors in TypeScript

## Type Mismatch Error

```typescript
let age: number = "twenty";
```

❌ Error:
```text
Type 'string' is not assignable to type 'number'
```

---

# 📌 Summary

## Key Points

- Type Annotation means explicitly defining datatype.
- Improves code quality and readability.
- Helps detect errors during development.
- Used for variables, functions, arrays, objects, classes, and interfaces.
- Essential in enterprise applications and automation frameworks.

---

# 📌 Final Conclusion

Type annotations are one of the most powerful features of TypeScript. They help developers write robust, maintainable, scalable, and error-free applications.

TypeScript annotations improve:
- Framework reliability
- Test stability
- Code readability

---
