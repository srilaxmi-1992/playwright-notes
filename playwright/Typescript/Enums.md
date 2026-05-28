# TypeScript Enums

# Introduction

Enums in TypeScript are used to store a group of related constant values.

Enums make code:

* More readable
* Easier to manage
* Safer than using random values

They are commonly used for:

* Status values
* User roles
* Directions
* API response states
* Fixed options

---

# What is an Enum?

An enum is a special TypeScript feature that allows us to define named constants.

---

# Basic Enum Syntax

```ts id="4g7m2x"
enum EnumName {
    VALUE1,
    VALUE2,
    VALUE3
}
```

---

# Example

```ts id="9k1v3p"
enum Direction {
    Up,
    Down,
    Left,
    Right
}

console.log(Direction.Up);
```

---

# Explanation

By default:

* `Up = 0`
* `Down = 1`
* `Left = 2`
* `Right = 3`

TypeScript automatically assigns numbers starting from `0`.

---

# 1. Numbered Enums

## Summary

Numbered enums store numeric values automatically or manually.

---

# Automatic Numbering

```ts id="1f5q8w"
enum Status {
    Pending,
    Approved,
    Rejected
}

console.log(Status.Pending);  // 0
console.log(Status.Approved); // 1
console.log(Status.Rejected); // 2
```

---

# Manual Numbering

```ts id="3n7x5u"
enum HttpStatus {
    OK = 200,
    NotFound = 404,
    ServerError = 500
}

console.log(HttpStatus.OK);
console.log(HttpStatus.NotFound);
```

---

# Explanation

You can assign custom numeric values manually.

This is useful for:

* HTTP status codes
* Database values
* Fixed IDs

---

# 2. Accessing Enum Values

Enums can be accessed using:

* Dot notation
* Bracket notation

---

# Dot Notation

```ts id="8m2v9r"
enum Color {
    Red,
    Green,
    Blue
}

console.log(Color.Red);
```

---

# Bracket Notation

```ts id="6q4t1n"
enum Color {
    Red,
    Green,
    Blue
}

console.log(Color["Green"]);
```

---

# Explanation

Both methods access enum values.

---

# 3. Enum Reverse Mapping (Both Ways)

## Summary

Numeric enums support reverse mapping.

This means:

* Name → Value
* Value → Name

---

# Example

```ts id="5p8c2y"
enum Direction {
    Up,
    Down,
    Left,
    Right
}

// Name to Value
console.log(Direction.Up);

// Value to Name
console.log(Direction[0]);
```

---

# Output

```ts id="2v7m4x"
0
Up
```

---

# Explanation

Numeric enums work in both directions:

* `Direction.Up` → `0`
* `Direction[0]` → `"Up"`

This is called reverse mapping.

---

# 4. String-Valued Enums

## Summary

String enums store string values instead of numbers.

---

# Syntax

```ts id="7t2m8k"
enum EnumName {
    VALUE1 = "string1",
    VALUE2 = "string2"
}
```

---

# Example

```ts id="4r9x1p"
enum UserRole {
    Admin = "ADMIN",
    User = "USER",
    Guest = "GUEST"
}

console.log(UserRole.Admin);
console.log(UserRole.User);
```

---

# Output

```ts id="1m6v7q"
ADMIN
USER
```

---

# Explanation

String enums:

* Use meaningful text values
* Improve readability
* Are commonly used in APIs and applications

---

# Important Note

String enums do NOT support reverse mapping.

---

# Example

```ts id="8x5n3u"
enum UserRole {
    Admin = "ADMIN"
}

console.log(UserRole.Admin);

// Not possible
// console.log(UserRole["ADMIN"]);
```

---

# Where We Use String Enums

## User Roles

```ts id="5n1r8p"
enum Role {
    Admin = "ADMIN",
    User = "USER"
}
```

---

## API Status

```ts id="2x6m4v"
enum ApiStatus {
    Loading = "LOADING",
    Success = "SUCCESS",
    Error = "ERROR"
}
```

---

## Payment Methods

```ts id="7m3q9k"
enum PaymentMethod {
    Cash = "CASH",
    Card = "CARD",
    UPI = "UPI"
}
```

---

# Complete Example

```ts id="9v2p6m"
// Number Enum
enum Direction {
    Up,
    Down,
    Left,
    Right
}

console.log(Direction.Up); // 0
console.log(Direction[0]); // Up

// String Enum
enum UserRole {
    Admin = "ADMIN",
    User = "USER",
    Guest = "GUEST"
}

console.log(UserRole.Admin);

// Accessing Enum Values
console.log(Direction.Left);
console.log(Direction["Right"]);
```

---

# Benefits of Enums

| Benefit             | Description                       |
| ------------------- | --------------------------------- |
| Readability         | Makes code easier to understand   |
| Type Safety         | Prevents invalid values           |
| Reusability         | Reuse constant values             |
| Better Organization | Groups related constants together |

---

# Final Summary

| Enum Type          | Example                             |
| ------------------ | ----------------------------------- |
| Number Enum        | `enum Status { Pending, Approved }` |
| Manual Number Enum | `OK = 200`                          |
| String Enum        | `Admin = "ADMIN"`                   |
| Reverse Mapping    | `Direction[0]`                      |

---

# Conclusion

Enums in TypeScript help organize related constant values.

They are useful for:

* Roles
* Status values
* API states
* Directions
* Fixed options

TypeScript provides:

* Numeric enums
* String enums
* Reverse mapping for numeric enums

Enums make applications cleaner, safer, and easier to maintain.
