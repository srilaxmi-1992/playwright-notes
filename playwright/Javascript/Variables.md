# JavaScript Variables – var, let, const (ES5 vs ES6)

## 🔹 1. var (ES5 – Old Style)

Used in older JavaScript (ES5) to declare variables.

```js id="var1"
var a = 5;
```

### Characteristics of `var`:

* ✅ Can be **re-declared**
* ✅ Can be **re-assigned**
* ⚠️ **Function scoped** (NOT block scoped)
* ⚠️ Supports **hoisting**

### Example:

```js id="var2"
var a = 5;
var a = 10; // re-declaration allowed
a = 20;     // re-assignment allowed
```

### Hoisting behavior:

```js id="var3"
console.log(a); // undefined
var a = 5;
```

👉 Internally behaves like:

```js
var a;
console.log(a); // undefined
a = 5;
```

---

## 🔹 2. let (ES6 – Modern JavaScript)

Introduced in ES6 for better scoping control.

```js id="let1"
let b = 10;
```

### Characteristics of `let`:

* ❌ Cannot be **re-declared in same scope**
* ✅ Can be **re-assigned**
* ✅ **Block scoped**
* ⚠️ Hoisted but stays in **Temporal Dead Zone (TDZ)**

### Example:

```js id="let2"
let b = 10;
b = 20; // re-assignment allowed

let b = 30; // ❌ Error: already declared
```

### TDZ behavior:

```js id="let3"
console.log(b); // ReferenceError
let b = 10;
```

---

## 🔹 3. const (ES6 – Constant Values)

Used for values that should not change.

```js id="const1"
const c = 100;
```

### Characteristics of `const`:

* ❌ Cannot be **re-declared**
* ❌ Cannot be **re-assigned**
* ✅ **Block scoped**
* ⚠️ Must be **initialized at declaration**

### Example:

```js id="const2"
const c = 100;
c = 200; // ❌ Error
```

---

## 🔹 Important Note (Objects & Arrays with const)

`const` does NOT make objects immutable — only the reference is fixed.

```js id="const3"
const obj = { name: "Alex" };
obj.name = "John"; // ✅ allowed
// obj = {} ❌ not allowed
```

---

## 🔹 Scope Comparison

| Keyword | Scope Type     | Re-declare | Re-assign | Hoisting Behavior    |
| ------- | -------------- | ---------- | --------- | -------------------- |
| var     | Function scope | ✅ Yes      | ✅ Yes     | undefined            |
| let     | Block scope    | ❌ No       | ✅ Yes     | TDZ (ReferenceError) |
| const   | Block scope    | ❌ No       | ❌ No      | TDZ (ReferenceError) |

---

## 🔹 Best Practice

* Prefer **const by default**
* Use **let when value changes**
* Avoid **var in modern JavaScript**

---

## 🔹 Key Takeaway

> Modern JavaScript (ES6+) encourages safer variable handling using `let` and `const`, reducing bugs caused by hoisting and scope issues in `var`.
