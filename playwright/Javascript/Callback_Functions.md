# Callback Functions in JavaScript

## 🧠 Functions in JavaScript

* Functions are **objects** in JavaScript (callable objects).

### Functions are first-class citizens:

1. They can be assigned to variables
2. They can be returned from other functions
3. They can be passed as arguments to other functions

---

## 🔁 Callback Function

A **callback** is a function passed as an argument to another function,
which is then executed later inside that function.

### Types of Callbacks:

* **Synchronous** → runs immediately, line by line execution , blocking code until done
* **Asynchronous** → runs later (e.g., timers, API calls), non-blocking

---

## 🔼 Higher-Order Function (HOF)

A function that:

* Takes another function as an argument, OR
* Returns a function

---

# 🧪 SYNCHRONOUS CALLBACK EXAMPLE

```js id="sync123"
// ---------------- SYNCHRONOUS CALLBACK EXAMPLE ----------------

function greet(myname, callback) {
    console.log("In greet method: hello --> " + myname);

    callback(); // synchronous callback (runs immediately)

    console.log("greet method is completed");
}

function myCallbackFn() {
    console.log("callback function invoked");
}

greet("Laxmi", myCallbackFn);
```

### 📌 Execution Order:

1. greet starts - Higher-Order Function (HOF)
2. logs "hello"
3. callback runs immediately - myCallbackFn()
4. logs "completed"

---

# ⏱️ ASYNCHRONOUS CALLBACK EXAMPLE

```js id="async456"
// ---------------- ASYNCHRONOUS CALLBACK EXAMPLE ----------------

function myHOF(callback) {
    console.log("Inside HOF: start");

    // setTimeout is built-in asynchronous code (non-blocking)
    // setTimeout functions in - built in node.js (actaully same support given by the browsers)
    setTimeout(() => {
        console.log("Executed after 6 seconds");
        callback(); // async callback
    }, 6000);

    console.log("After scheduling async task (does NOT wait)");

    let b = 80 + 100;
    console.log("Value of b:", b);
}

function asyncCallbackFn() {
    console.log("Inside async callback function");
}

myHOF(asyncCallbackFn);
```

### 📌 Execution Order:

1. "Inside HOF: start"
2. setTimeout scheduled (non-blocking)
3. "After scheduling async task"
4. "Value of b: 180"

**After 6 seconds:**
5. "Executed after 6 seconds"
6. "Inside async callback function"

---

## ⚠️ Callback Hell (Problem)

```js id="hell789"
setTimeout(() => {
  console.log("Step 1");
  setTimeout(() => {
    console.log("Step 2");
    setTimeout(() => {
      console.log("Step 3");
    }, 1000);
  }, 1000);
}, 1000);
```

👉 Too many nested callbacks make code hard to read and maintain.

---

## ✅ Modern Alternatives

* Promises
* async/await

---

## 🧠 Summary

* Functions are first-class citizens
* Callbacks = functions passed into other functions
* Can be synchronous or asynchronous
* Used heavily in async programming
* May lead to callback hell (solved by Promises / async-await)
