# 🔁 JavaScript Loops — Explained Clearly

Loops are used to execute a block of code repeatedly until a condition is met.
They help avoid writing repetitive code and make programs more efficient and readable.
Every loop typically involves **initialization, condition (execution check), and increment/decrement**.

---

## 🔄 while Loop

The `while` loop runs **as long as the condition is true**.
The condition is checked **before** each iteration, so it may run zero times if the condition is false initially.
You must manually update the variable (increment/decrement) to avoid infinite loops.

```js id="while01"
let count = 20; // initialization

while (count > 0) { // condition
    console.log(count); // execution
    count--; // decrement
}
```

**Summary:**
Use `while` when you don’t know how many times the loop will run in advance.
Make sure the condition eventually becomes false to stop the loop.

---

## 🔁 do...while Loop

The `do...while` loop executes the block **at least once**, even if the condition is false.
The condition is checked **after** execution.
Useful when the code must run at least one time regardless of the condition.

```js id="dowhile01"
let num = 10; // initialization

do {
    console.log(num); // execution
    num--; // decrement
} while (num > 0); // condition
```

**Summary:**
Best used when one execution is guaranteed or required.
Common in scenarios like user input validation or menus.

---

## 🔢 for Loop

The `for` loop is the most commonly used loop when the number of iterations is known.
It combines **initialization, condition, and increment/decrement** in a single line.
This makes the loop more compact and easier to read.

```js id="for01"
for (let i = 0; i < 5; i++) {
    console.log(i);
}
```

**Summary:**
Ideal for counting loops or when working with arrays and indexes.
Keeps loop structure clean and organized.

---

## 🧠 Key Concepts (Important)

* **Initialization** → Starting point of the loop (`let i = 0`)
* **Condition** → Determines if loop should continue (`i < 5`)
* **Increment/Decrement** → Updates loop variable (`i++`, `count--`)

---

## 🚀 Quick Comparison

| Loop Type  | Condition Check | Runs At Least Once | Best Use Case      |
| ---------- | --------------- | ------------------ | ------------------ |
| while      | Before          | ❌ No               | Unknown iterations |
| do...while | After           | ✅ Yes              | Must run once      |
| for        | Before          | ❌ No               | Known iterations   |

---
