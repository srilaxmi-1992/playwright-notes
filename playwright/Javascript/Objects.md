# JavaScript Objects – Complete Tutorial Notes

## Object Initialization

Objects in JavaScript are collections of key-value pairs used to store structured data.

```js
let address = {
    city: "sarasota",
    state: "florida",
    zipcode: 34238
};
```

**Summary:**
An object is created using curly braces `{}` and contains properties defined as `key: value`.

---

## Nested Objects

Objects can contain other objects as properties, enabling hierarchical data structures.

```js
let name = {
    firstName: "John",
    lastName: "Doe",
    age: 30,
    address: address
};
```

**Summary:**
Nested objects allow you to group related data inside a parent object.

---

## Accessing Object Properties (Dot Notation)

You can access object properties using the dot (`.`) operator.

```js
console.log(name.firstName);
console.log(name.lastName);
console.log(name.age);
console.log(name.address.city);
```

**Summary:**
Dot notation is the most common and readable way to access object properties.

---

## Accessing Object Properties (Bracket Notation)

You can also access properties using square brackets `[]`.

```js
console.log(name['firstName']);
console.log(name['address']);
console.log(name['address']['city']);
```

**Summary:**
Bracket notation is useful when property names are dynamic or stored in variables.

---

## Adding New Properties

New properties can be added to an object dynamically.

```js
let car = {
    brand: "Tesla",
    model: "Model 3"
};

car.year = 2024;
console.log(car);
```

**Summary:**
JavaScript objects are mutable, allowing properties to be added after creation.

---

## Updating Existing Properties

Existing object properties can be modified easily.

```js
let employee = {
    name: "John",
    role: "QA"
};

employee.role = 'Automation QA';
console.log(employee);
```

**Summary:**
You can update property values using dot or bracket notation.

---

## Deleting Properties

Properties can be removed using the `delete` keyword.

```js
let user = {
    name: "Alex",
    age: 30,
    location: "USA"
};

delete user.location;
console.log(user);
```

**Summary:**
The `delete` operator removes a property from an object.

---

## Checking Property Existence

You can check if a property exists using the `in` operator.

```js
let laptop = {
    brand: "HP",
    ram: "16GB"
};

if ('ram' in laptop)
    console.log("exists");
else
    console.log("not exists");
```

**Summary:**
The `in` operator returns `true` if the specified property exists in the object.

---

## Iterating Over Objects (for...in loop)

The `for...in` loop is used to iterate through object properties.

```js
for (const key in name) {
    console.log(key);
    console.log(name[key]);
}
```

**Summary:**
The `for...in` loop iterates over all enumerable properties of an object.

---

## Objects with Arrays

Objects can store arrays as property values.

```js
let objarr = {
    name: "sri",
    age: 33,
    grad: true,
    data: [25, 9, 1992]
};

console.log(objarr.data[1]);
```

**Summary:**
Arrays inside objects allow storing multiple related values under a single key.

---

## Objects with Functions (Methods)

Objects can also contain functions, known as methods.

```js
let obj = {
    name: "playwright",
    show: function () {
        return "hey";
    }
};

console.log(obj.show());
```

**Summary:**
Functions inside objects are called methods and define object behavior.

---

## Final Key Takeaways

* Objects store data in **key-value pairs**
* Properties can be **added, updated, or deleted dynamically**
* Use **dot notation** for simplicity and **bracket notation** for flexibility
* Objects support **nested structures, arrays, and functions**
* Iteration can be done using the **for...in loop**

---
