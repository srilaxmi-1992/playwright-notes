# JavaScript Operators Quick Summary

* **Arithmetic Operators (`+ - * / %`)** → Perform basic math operations.
  Example: `let sum = 5 + 3; // 8`

* **Relational Operators (`> < >= <=`)** → Compare values and return boolean.
  Example: `10 > 5; // true`

* **Equality (`==`)** → Compares values with type coercion.
  Example: `5 == "5"; // true`

* **Strict Equality (`===`)** → Compares value + type (no coercion).
  Example: `5 === "5"; // false`

* **Ternary (`condition ? a : b`)** → Short if-else.
  Example: `let status = age >= 18 ? "Adult" : "Minor";`

* **Increment (`++`) / Decrement (`--`)** → Increase/decrease by 1.
  Example: `let x = 5; x++; // 6`

* **Assignment (`=, +=, -=, *=, /=`)** → Assign/update values.
  Example: `let x = 10; x += 5; // 15`

* **Logical (`&& || !`)** → Combine boolean conditions.
  Example: `true && false; // false`

* **Typeof (`typeof`)** → Returns data type.
  Example: `typeof 42; // "number"`

---

```javascript
let name = "QA Masters";
let age = 30;
let isActive = true;
let city;
let value = null;
let students = ["Rahul", "Priya"];
let employee = { name: "John", role: "Tester" };

console.log(typeof name); // string
console.log(typeof age); // number
console.log(typeof isActive); // boolean
console.log(typeof city); // undefined
console.log(typeof value); // object
console.log(typeof students); // object
console.log(typeof employee); // object
```
