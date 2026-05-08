# Async Callbacks Internals in JavaScript

## 🧠 JavaScript Execution Model

JavaScript is **single-threaded**, meaning it executes one task at a time using:

* **Call Stack** → Executes functions
* **Web APIs / Node APIs** → Handle async operations (timers, fetch, etc.)
* **Callback Queue (Macrotask Queue)** → Stores async callbacks
* **Microtask Queue** → Higher priority queue (Promises, MutationObserver)
* **Event Loop** → Coordinates everything

---

## 📦 Call Stack (Execution Context)

* When a JS program starts:

  * A **Global Execution Context (GEC)** is created and pushed to the stack

* When a function is called:

  * A new **Function Execution Context** is pushed to the stack

* When execution finishes:

  * It is **popped off the stack**

```js id="stack001"
function one() {
  two();
}

function two() {
  console.log("Inside two");
}

one();
```

### Flow:

1. Global Execution Context pushed
2. `one()` pushed
3. `two()` pushed
4. `two()` executed → popped
5. `one()` popped
6. Global context remains

---

## ⏱️ Async Functions Internals

Async functions like:

* `setTimeout`
* `setInterval`
* `fetch`
* DOM events

👉 **DO NOT run on the call stack**

Instead, they are handled by:

* **Browser Web APIs** OR
* **Node.js APIs (libuv)**

---

## 🔄 Step-by-Step Async Flow

```js id="async002"
console.log("Start");

setTimeout(() => {
  console.log("Timer done");
}, 2000);

console.log("End");
```

### Execution Steps:

1. `"Start"` → pushed to stack → executed
2. `setTimeout()` → registered in **Web APIs / Node APIs (Timer Registry)**
3. Timer starts (2 seconds) outside stack
4. `"End"` executes immediately

⏳ After 2 seconds:
5. Callback moves to **Callback Queue (Macrotask Queue)**
6. **Event Loop checks the Call Stack**
7. If stack is empty → moves callback to stack
8. `"Timer done"` executes

---

## 🔁 Event Loop (Core Concept)

The **Event Loop** continuously checks:

👉 “Is the Call Stack empty?”

* If **NO** → wait
* If **YES** → take task from queue and push to stack

---

## 📬 Queues in JavaScript

### 1. Macrotask Queue (Callback Queue)

* setTimeout
* setInterval
* setImmediate (Node.js)
* DOM events
* fetch

### 2. Microtask Queue (Higher Priority ⚡)

* Promises (`.then`, `.catch`)
* `queueMicrotask`

👉 Microtasks run **before** macrotasks

---

## ⚡ Microtask Example

```js id="micro003"
console.log("Start");

setTimeout(() => console.log("Timeout"), 0);

Promise.resolve().then(() => console.log("Promise"));

console.log("End");
```

### Output:

```text
Start
End
Promise
Timeout
```

👉 Even with `0ms`, `setTimeout` waits behind microtasks.

---

## 🏢 Real-Time Analogy (Restaurant)

Imagine a restaurant:

* 👨‍🍳 **Chef** → Call Stack
* 📋 **Order Manager** → Event Loop
* 🧾 **Order List** → Callback Queue
* ⚡ **VIP Orders** → Microtask Queue
* 🏭 **Kitchen Staff** → Web APIs / Node APIs

### Flow:

1. Chef handles current order (stack)
2. Long tasks (like baking) go to kitchen (Web APIs)
3. When ready → placed in order queue
4. Event loop checks:

   * If chef is free → picks next order
   * VIP orders (microtasks) served first

---

## 🔍 Key Points

* JS is single-threaded but handles async via APIs
* Async tasks run **outside the call stack**
* Event loop manages execution order
* Microtasks > Macrotasks in priority
* Call stack must be empty before callbacks execute

---

## 🧠 Summary

* Call Stack executes synchronous code
* Async APIs handle timers/fetch outside stack
* Completed async tasks go to queues
* Event Loop pushes them back to stack
* Microtasks run before macrotasks

---

## 🚀 One-Line Memory Trick

👉 **"Stack → API → Queue → Event Loop → Stack"**
