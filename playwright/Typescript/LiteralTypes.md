# TypeScript Literal Types

# Introduction

Literal types in TypeScript allow variables to store only specific fixed values.

Normally:

* `string` accepts any text
* `number` accepts any number
* `boolean` accepts both `true` and `false`

But literal types restrict variables to exact values only.

This helps:

* Prevent invalid values
* Improve code safety
* Improve auto-completion

---

# What are Literal Types?

Literal types are exact values used as types.

## Example

```ts id="4o5w3g"
let direction: "left";

direction = "left"; // Correct
direction = "right"; // Error
```

Here:

* `"left"` is a literal type
* Only `"left"` is allowed

---

# 1. String Literal Types

## Summary

String literal types allow only specific string values.

---

## Syntax

```ts id="5n2r9u"
let variableName: "value1" | "value2";
```

---

## Example

```ts id="u5n1qv"
let theme: "light" | "dark";

theme = "light"; // Correct
theme = "dark";  // Correct
theme = "blue";  // Error
```

---

## Explanation

The variable `theme` can store only:

* `"light"`
* `"dark"`

Any other value causes an error.

---

## Where We Use String Literal Types

### Theme Selection

```ts id="4d3x5m"
let theme: "light" | "dark";
```

---

### API Request Methods

```ts id="x8m2pq"
let method: "GET" | "POST" | "PUT" | "DELETE";
```

---

### User Roles

```ts id="q7r4wn"
let role: "admin" | "user" | "guest";
```

---

# 2. Boolean Literal Types

## Summary

Boolean literal types allow only:

* `true`
  OR
* `false`

---

## Syntax

```ts id="z8v5kc"
let variableName: true;
```

or

```ts id="m6u1op"
let variableName: false;
```

---

## Example

```ts id="2r9pxt"
let isCompleted: true;

isCompleted = true;  // Correct
isCompleted = false; // Error
```

---

## Explanation

The variable accepts only one boolean value.

---

## Where We Use Boolean Literal Types

### Fixed Success State

```ts id="7f2m9w"
let success: true;
```

---

### Authentication Status

```ts id="v3q8jc"
let loggedOut: false;
```

---

# 3. Number Literal Types

## Summary

Number literal types allow only specific numeric values.

---

## Syntax

```ts id="5y1nke"
let variableName: 1 | 2 | 3;
```

---

## Example

```ts id="4p7zxd"
let diceValue: 1 | 2 | 3 | 4 | 5 | 6;

diceValue = 3; // Correct
diceValue = 7; // Error
```

---

## Explanation

The variable can store only the allowed numbers.

---

## Where We Use Number Literal Types

### Dice Values

```ts id="y6m2ca"
let dice: 1 | 2 | 3 | 4 | 5 | 6;
```

---

### Rating Systems

```ts id="j8u5np"
let rating: 1 | 2 | 3 | 4 | 5;
```

---

### HTTP Success Codes

```ts id="7o1vmb"
let statusCode: 200 | 201 | 204;
```

---

# Literal Types in Functions

Literal types are commonly used in function parameters.

---

## Example

```ts id="1m7xzr"
function setAlignment(alignment: "left" | "center" | "right") {
    console.log(alignment);
}

setAlignment("left");   // Correct
setAlignment("bottom"); // Error
```

---

# Benefits of Literal Types

| Benefit                | Description                  |
| ---------------------- | ---------------------------- |
| Type Safety            | Prevents invalid values      |
| Better Auto-completion | Editors suggest valid values |
| Error Prevention       | Reduces bugs                 |
| Cleaner Code           | Makes code easier to read    |

---

# Complete Example

```ts id="6x3m8r"
// String Literal Type
let theme: "light" | "dark";

theme = "light";

// Boolean Literal Type
let isLoading: true;

isLoading = true;

// Number Literal Type
let rating: 1 | 2 | 3 | 4 | 5;

rating = 5;

// Function with Literal Types
function setMode(mode: "online" | "offline") {
    console.log(`Mode: ${mode}`);
}

setMode("online");
```

---

# Final Summary

| Literal Type    | Example         |
| --------------- | --------------- |
| String Literal  | `"yes" \| "no"` |
| Boolean Literal | `true`          |
| Number Literal  | `1 \| 2 \| 3`   |

---

# Conclusion

Literal types in TypeScript restrict variables to fixed values.

They are useful for:

* Themes
* User roles
* API methods
* Status values
* Function parameters
* Fixed numeric values

Using literal types makes applications safer and easier to maintain.
