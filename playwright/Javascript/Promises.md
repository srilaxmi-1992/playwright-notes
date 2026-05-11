# JavaScript — Callbacks vs Promises

## What is a Callback?

A **callback** is a function passed into another function to be executed later — either synchronously or asynchronously.

```js
function fetchData(callback) {
  setTimeout(() => {
    callback("Data received");
  }, 1000);
}

fetchData((data) => {
  console.log(data); // "Data received"
});
```

### ❌ The Problem: Callback Hell

When multiple async operations depend on each other, callbacks nest deeply — making code hard to read and maintain.

```js
loginUser("john", (user) => {
  getUserProfile(user.id, (profile) => {
    getOrders(profile.id, (orders) => {
      getOrderDetails(orders[0].id, (details) => {
        console.log(details); // deeply nested, messy
      });
    });
  });
});
```

Problems with callbacks:
- Deep nesting (the "pyramid of doom")
- Messy, scattered error handling
- Hard to read and maintain

---

## What is a Promise?

Introduced in **ES6**, a **Promise** is an object representing the **eventual result** of an asynchronous operation.

### Promise States

| State       | Meaning                                      |
|-------------|----------------------------------------------|
| `Pending`   | Initial state — operation not yet complete   |
| `Fulfilled` | Operation succeeded — `resolve()` was called |
| `Rejected`  | Operation failed — `reject()` was called     |

### Basic Structure

```js
const myPromise = new Promise((resolve, reject) => {
  // async logic here
  const success = true;

  if (success) {
    resolve("Operation successful!");
  } else {
    reject("Something went wrong.");
  }
});
```

### Consuming a Promise

```js
myPromise
  .then((result) => {
    console.log(result);   // runs when resolved
  })
  .catch((error) => {
    console.error(error);  // runs when rejected
  })
  .finally(() => {
    console.log("Done");   // always runs
  });
```

---

## Real-World Example: Fetching User Data from an API

Without Promises (callback approach):

```js
// Deeply nested, hard to follow
getUser(1, (user) => {
  getPosts(user.id, (posts) => {
    getComments(posts[0].id, (comments) => {
      console.log(comments);
    });
  });
});
```

With Promises (clean chaining):

```js
function getUser(userId) {
  return fetch(`https://jsonplaceholder.typicode.com/users/${userId}`)
    .then((res) => res.json());
}

function getPosts(userId) {
  return fetch(`https://jsonplaceholder.typicode.com/posts?userId=${userId}`)
    .then((res) => res.json());
}

function getComments(postId) {
  return fetch(`https://jsonplaceholder.typicode.com/comments?postId=${postId}`)
    .then((res) => res.json());
}

getUser(1)
  .then((user) => {
    console.log("User:", user.name);
    return getPosts(user.id);
  })
  .then((posts) => {
    console.log("First post:", posts[0].title);
    return getComments(posts[0].id);
  })
  .then((comments) => {
    console.log("First comment:", comments[0].body);
  })
  .catch((error) => {
    console.error("Error:", error);
  })
  .finally(() => {
    console.log("Request complete.");
  });
```

---

##  Example: Coffee Machine


> Each step waits for the previous one to resolve before starting — this is **sequential async chaining** using Promises.

```js
function startMachine() {
  return new Promise((resolve, reject) => {
    setTimeout(() => resolve("Machine Started"), 2000);
  });
}

function grindBeans() {
  return new Promise((resolve, reject) => {
    setTimeout(() => resolve("Grinding coffee beans"), 2000);
  });
}

function boilWater() {
  return new Promise((resolve, reject) => {
    setTimeout(() => resolve("Boiling water"), 2000);
  });
}

function brewCoffee() {
  return new Promise((resolve, reject) => {
    setTimeout(() => resolve("Brewing coffee"), 2000);
  });
}

function pourCoffee() {
  return new Promise((resolve, reject) => {
    setTimeout(() => resolve("Pouring coffee into cup"), 2000);
  });
}

startMachine()
  .then((result) => { console.log(result); return grindBeans(); })
  .then((result) => { console.log(result); return boilWater(); })
  .then((result) => { console.log(result); return brewCoffee(); })
  .then((result) => { console.log(result); return pourCoffee(); })
  .then((result) => { console.log(result); console.log("☕ Coffee is ready!"); })
  .catch((error) => { console.error("Error:", error); })
  .finally(() => console.log("Done"));
```

**Output (each line after ~2s):**
```
Machine Started
Grinding coffee beans
Boiling water
Brewing coffee
Pouring coffee into cup
☕ Coffee is ready!
Done
```


---

## Key Benefits of Promises

| Feature              | Callbacks          | Promises              |
|----------------------|--------------------|-----------------------|
| Readability          | ❌ Deeply nested   | ✅ Flat chaining       |
| Error handling       | ❌ Per-callback    | ✅ Single `.catch()`   |
| Composability        | ❌ Hard to compose | ✅ Easy to chain       |
| Parallel execution   | ❌ Manual          | ✅ `Promise.all()`     |

---

## Bonus: Promise.all() — Run in Parallel

When steps are **independent**, run them simultaneously:

```js
Promise.all([grindBeans(), boilWater()])
  .then(([beansResult, waterResult]) => {
    console.log(beansResult); // "Grinding coffee beans"
    console.log(waterResult); // "Boiling water"
    return brewCoffee();
  })
  .then((result) => console.log(result))
  .catch((error) => console.error("One step failed:", error));
```

> `Promise.all()` rejects immediately if **any** one promise rejects.  
> Use `Promise.allSettled()` if you want all results regardless of failure.

---

## Summary

- Use **callbacks** only for simple, single-level async tasks
- Use **Promises** when async operations need to be **chained or composed**
- Always include a `.catch()` to handle errors
- Use `Promise.all()` to **run independent async tasks in parallel**
- Next step → learn **`async/await`**, which is syntactic sugar over Promises and makes async code look synchronous
