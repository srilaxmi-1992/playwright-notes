# Async Await Example in JavaScript

async/await is a cleaner way to handle asynchronous operations using Promises.

## Code

```js
async function orderFood() {

    return new Promise((resolve) => {
        setTimeout(() => {
            resolve('Food ordered')
        }, 1000)
    })
}

function prepareFood() {

    return new Promise((resolve) => {
        setTimeout(() => {
            resolve('Food prepared')
        }, 2000)
    })
}

function deliverFood() {

    return new Promise((resolve) => {
        setTimeout(() => {
            resolve('Food delivered')
        }, 1000)
    })
}

async function food() {

    try {

        let res = await orderFood()
        console.log(res)

        res = await prepareFood()
        console.log(res)

        res = await deliverFood()
        console.log(res)

    } catch (err) {

        console.log(`getting error while doing functions ${err}`)
    }
}

food()
```

---

# Step-by-Step Explanation

## 1. `orderFood()`

```js
async function orderFood()
```
- When a function is marked async: it automatically returns a Promise.
- Async function returning a Promise
- Simulates ordering food
- Uses `setTimeout()` for delay
- Resolves after 1 second

Output:
```txt
Food ordered
```

---

## 2. `prepareFood()`

```js
function prepareFood()
```

- Returns a Promise manually
- Simulates preparing food
- Takes 2 seconds

Output:
```txt
Food prepared
```

---

## 3. `deliverFood()`

```js
function deliverFood()
```

- Returns a Promise
- Simulates delivery process
- Takes 1 second

Output:
```txt
Food delivered
```

---

# Main Function: `food()`

```js
async function food()
```

This function controls the complete flow using:
- `async`
- `await`
- `try/catch`

---

# Execution Flow

## Step 1

```js
let res = await orderFood()
```

- JS pauses here
- Waits for Promise to resolve
- After 1 second:
```txt
Food ordered
```

gets printed.

---

## Step 2

```js
res = await prepareFood()
```

- Waits for food preparation
- After 2 seconds:
```txt
Food prepared
```

gets printed.

---

## Step 3

```js
res = await deliverFood()
```

- Waits for delivery
- After 1 second:
```txt
Food delivered
```

gets printed.

---

# Final Output Order

```txt
Food ordered
Food prepared
Food delivered
```

---

# Total Time Taken

| Function | Delay |
|---|---|
| orderFood | 1 sec |
| prepareFood | 2 sec |
| deliverFood | 1 sec |

Total:
```txt
4 seconds
```

Because each `await` waits sequentially.

---

# Important Concepts Used

## 1. Promise

Represents a future value.

```js
new Promise((resolve) => {})
```

---

## 2. async

Makes function automatically return a Promise. Even though we returned a string,
JS wraps it inside: Promise.resolve("Hello")

```js
async function hello() {
    return "Hello";
}

console.log(hello());
```

---

## 3. await

await pauses execution of the async function until Promise resolves.

```js
await somePromise
```

---

## 4. try/catch

Handles async errors safely.

```js
try {

} catch(err) {

}
```

## Promise vs Async Await

Promise 
```js
getData()
   .then((res) => {
       console.log(res);
   })
   .catch((err) => {
       console.log(err);
   });
```

Async Await
```js
try {

   const res = await getData();
   console.log(res);

} catch(err) {

   console.log(err);
}
```


---

# Real-World Analogy

Think of food delivery app process:

1. Order food
2. Wait for restaurant to prepare
3. Wait for delivery partner
4. Receive food

Each step depends on previous step.

That is why `await` is useful for sequential async operations.

---

# Important Interview Point

## Does `await` block JavaScript?

❌ No

It only pauses:
```txt
that async function
```

JavaScript event loop still continues running other tasks.

---

# Short Summary

- `async` makes function return Promise
- `await` waits for Promise completion
- Execution happens sequentially
- `try/catch` handles async errors
- Useful for API calls, DB calls, timers, file operations
