# 🔀 JavaScript Conditional Statements

Conditional statements allow your program to make decisions based on conditions.
They control the flow of execution, running different blocks of code depending on whether conditions are true or false.

---

## ✅ if...else Statement

The `if...else` statement evaluates a condition and executes code based on the result.
If the condition is `true`, the `if` block runs; otherwise, the `else` block executes.
This is the most basic and commonly used decision-making structure.

```js id="ifelse01"
let age = 25;

if (age > 18) {
    console.log("Eligible for vote");
} else {
    console.log("Not eligible for vote");
}
```

---

## 🔁 if...else if...else Ladder

Used when you need to check multiple conditions sequentially.
Once a condition is true, the rest are skipped, improving efficiency.
Useful for range checks or multiple decision paths.

```js id="elseif01"
let marks = 75;

if (marks >= 90) {
    console.log("Grade A");
} else if (marks >= 60) {
    console.log("Grade B");
} else if (marks >= 40) {
    console.log("Grade C");
} else {
    console.log("Fail");
}
```

---

## 🔀 switch Statement

The `switch` statement is used when comparing one value against multiple possible cases.
It improves readability compared to many `else if` conditions.
Each `case` must include a `break` to prevent fall-through behavior.

```js id="switch01"
let browser = "firefox";

switch (browser) {
    case "chrome":
        console.log("Chrome selected");
        break;
    case "firefox":
        console.log("Firefox selected");
        break;
    case "edge":
        console.log("Edge selected");
        break;
    default:
        console.log("No browser selected");
}
```

---

## ⚡ Ternary Operator (Short if...else)

A compact way to write simple `if...else` conditions in a single line.
Best used for short, simple decisions to keep code clean.
Avoid using it for complex logic as it can reduce readability.

```js id="ternary01"
let age = 20;

let result = (age > 18) ? "Eligible" : "Not eligible";
console.log(result);
```

---

## 🧠 Key Notes

* Use **if...else** for flexible and complex conditions
* Use **switch** when checking a single value against many options
* Use **ternary** for short and simple conditions
* Always use `break` in switch to avoid unintended execution

---
