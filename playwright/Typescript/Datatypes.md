# TypeScript Primitive and Non-Primitive Data Types

## What are Data Types?

Data types define the type of value a variable can store.

In TypeScript, data types are mainly divided into:

1. Primitive Data Types
2. Non-Primitive Data Types

---

# 1. Primitive Data Types

Primitive data types store single values.

## Primitive Types in TypeScript

- number
- string
- boolean
- null
- undefined
- any
- union type
- void

---

# number

Used to store:
- integers
- decimal values
- large numbers

## Real-Time Examples
- age
- salary
- marks
- mobile number
- product price

```ts
let num: number = 25.0
let age: number = 33
let salary: number = 85000.50
let mobile: number = 9876543210

console.log(age)
console.log(typeof age)
```

---

# string

Used to store sequence of characters.

## Real-Time Examples
- employee name
- city
- email
- company name

```ts
let fname: string = "srilaxmi"
let lname: string = "amaraneni"

let fullname: string = `${fname} ${lname}`

console.log(fullname)
```

---

# boolean

Stores only:
- true
- false

## Real-Time Examples
- login status
- payment status
- student status
- order delivered

```ts
let flag: boolean = true
let isStudent: boolean = false

console.log(flag)
console.log(isStudent)
```

---

# undefined

A variable declared but value not assigned.

## Real-Time Example
- data not available yet
- optional values

```ts
let a: undefined

console.log(a)
```

---

# null

Represents intentionally empty value.

## Real-Time Example
- no profile picture
- no manager assigned

```ts
let b: null = null

console.log(b)
```

---

# any

Can store any datatype.

Use carefully because it removes TypeScript type safety.

## Real-Time Example
- API response data
- third-party libraries

```ts
let c: any = 20

c = "yuvika"

c = true

console.log(c)
```

---

# Union Type

Allows multiple datatypes for one variable.

Syntax:

```ts
datatype1 | datatype2
```

## Real-Time Example
- employee id can be string or number

```ts
let id: string | number | boolean = "college"

id = 1001

id = true

console.log(id)
```

---

# void

Used mainly with functions.

Means function does not return any value.

```ts
function greet(): void {
    console.log("Hello Typescript")
}

greet()
```

---

# 2. Non-Primitive Data Types

Non-primitive data types store multiple values or complex data.

## Types
- object
- array
- function

---

# Objects

Objects store data in key-value pairs.

## Real-Time Examples
- employee details
- student information
- product details

```ts
const employee: {
    empId: number
    empName: string
    department: string
    isWorking: boolean
} = {
    empId: 101,
    empName: "Naresh",
    department: "QA",
    isWorking: true
}

console.log(employee)
```

---

# Arrays

Arrays store multiple values of same datatype.

## Real-Time Examples
- colors
- marks
- employee names

```ts
let colors: string[] = ["red", "blue", "green"]

let marks: number[] = [85, 90, 95]

console.log(colors)
console.log(marks)
```

---

# Summary Table

| Data Type | Example |
|---        |---|
| number | 100, 25.5 |
| string | "Naresh" |
| boolean | true |
| undefined | variable without value |
| null | empty value |
| any | any datatype |
| union | string   | number |
| void | no return value |
| object | employee details |
| array | list of values |

---

# Advantages of TypeScript Data Types

- Compile-time type checking
- Better IntelliSense support
- Reduces runtime errors
- Improves readability
- Better maintainability
- Provides type safety

---

# Conclusion

TypeScript data types help developers write cleaner, safer, and more maintainable code.

Primitive types store single values, while non-primitive types store collections and complex data structures.