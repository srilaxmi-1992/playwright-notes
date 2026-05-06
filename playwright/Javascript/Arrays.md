# 📦 JavaScript Arrays — Quick Reference & Summary

## 🧱 Creating an Array

```js
const fruits = ["apple", "banana", "watermelon", "pineapple", "strawberry"]
```

**Summary:** Arrays are used to store multiple values in a single variable, keeping them in an ordered structure.
Each value is assigned an index, starting from 0, making it easy to organize and access grouped data.
They are flexible and can hold different data types, including numbers, strings, and objects.

---

## 🔢 Accessing Elements

```js
console.log(fruits[0]) // first item
console.log(fruits[2]) // third item
```

**Summary:** Array elements are accessed using their index, with the first element at position 0.
This allows direct retrieval of any item without looping through the entire array.
It’s a fast and efficient way to work with specific positions in a dataset.

---

## ✏️ Modifying Elements

```js
fruits[1] = "orange"
```

**Summary:** Arrays in JavaScript are mutable, meaning their contents can be changed after creation.
You can update any element by assigning a new value to its index.
This makes arrays useful for dynamic data that changes over time.

---

## 📏 Array Length

```js
console.log(fruits.length)
```

**Summary:** `.length` returns total number of elements.
The .length property returns the total number of elements in the array.
It updates automatically whenever items are added or removed.
This is commonly used in loops and validations.

---

## ➕ Add Elements

### End

```js
fruits.push("grape")
```

**Summary:** Adds item to the end

### Start

```js
fruits.unshift("kiwi")
```

**Summary:** Adds item to the beginning.
Methods like .push() and .unshift() allow adding elements to the end or beginning of an array.
These operations modify the original array directly.
They are useful when building or expanding lists dynamically.

---

## ➖ Remove Elements

### End

```js
fruits.pop()
```

**Summary:** Removes last item.

### Start

```js
fruits.shift()
```

**Summary:** Removes first item.
Methods such as .pop() and .shift() remove elements from the end or beginning.
These also mutate the original array and return the removed element.
They are commonly used for managing stacks and queues.

---

## 🔁 Looping Through Arrays

### Traditional Loop

```js
for (let i = 0; i < fruits.length; i++) {
  console.log(fruits[i])
}
```

**Summary:** Full control using index.

### For...of Loop

```js
for (const fruit of fruits) {
  console.log(fruit)
}
```

**Summary:** Cleaner way to iterate values.

### forEach

```js
fruits.forEach(fruit => console.log(fruit))
```

**Summary:** Executes function for each element (no return).

---

## 🔍 Searching

### Includes

```js
fruits.includes("banana")
```

**Summary:** Checks if value exists (true/false).

### indexOf

```js
fruits.indexOf("pineapple")
```

**Summary:** Returns index or -1 if not found.

---

## 🧹 Filtering

```js
let evenfr = fruits.filter(fruit => fruit.length % 2 === 0)
```

**Summary:** Returns new array with matching condition.
The .filter() method creates a new array containing elements that meet a condition.
It does not modify the original array, making it safe for data transformations.
This is commonly used for extracting specific subsets of data.

---

## 🔄 Mapping

```js
let doubled = nums.map(num => num * 2)
```

**Summary:** Transforms each element into a new array.
The .map() method transforms each element in an array and returns a new array.
It is useful when you need to modify all elements in a consistent way.
Unlike loops, it keeps the code clean and functional.

---

## ➕ Reducing

```js
let sum = nums.reduce((acc, curr) => acc + curr, 0)
```

**Summary:** Reduces array to a single value (sum, total, etc.).
The .reduce() method processes all elements and reduces them into a single value.
It is often used for calculations like sums, totals, or aggregations.
This method is powerful for handling complex data transformations.

---

## ✂️ Slicing

```js
nums.slice(0, 3)
```

**Summary:** Returns a shallow copy of part of array (non-mutating).
The .slice() method extracts a portion of an array and returns a new one.
It does not change the original array, making it non-destructive.
Useful for copying or selecting specific sections of data.

---

## 🔗 Concatenation

```js
a.concat(b)
```

**Summary:** Merges arrays into a new one.
The .concat() method merges two or more arrays into a new array.
It does not modify the original arrays, preserving existing data.
This is helpful when combining datasets.

---

## 🔤 Sorting

```js
fruits.sort()
```

**Summary:** Sorts array (mutates original).
The .sort() method arranges elements in place, modifying the original array.
By default, it sorts values as strings, which may cause unexpected results with numbers.
A compare function is often needed for accurate numeric sorting.

⚠️ Numbers:

```js
n.sort((a, b) => a - b)
```

**Summary:** Needed for correct numeric sorting.

---

## 🔁 Reversing

```js
n.reverse()
```

**Summary:** Reverses array in place (mutates).
The .reverse() method flips the order of elements in the array.
It mutates the original array instead of creating a new one.
Often used after sorting or for displaying data in reverse order.

---

## 🧑‍💻 Array of Objects

```js
const users = [
  { name: "John", age: 20 },
  { name: "Sara", age: 25 }
];

users.map(user => console.log(user.name))
```

**Summary:** Arrays can store objects; use `.map()` to extract data.
Arrays can store objects, allowing you to manage structured data collections.
You can use methods like .map() to extract or transform object properties.
This is widely used in real-world applications like user data handling.

---

## 🧠 Key Takeaways

* Arrays are **mutable** and **indexed**
* Use **map/filter/reduce** for functional programming
* Some methods **mutate** (push, pop, sort), others don’t (slice, map, filter)
* Choose loop style based on need (control vs readability)

---
