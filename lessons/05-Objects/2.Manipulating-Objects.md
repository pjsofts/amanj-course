---
title: "Manipulating Javascript Objects"
---

**Lesson 2: Manipulating JavaScript Objects**

Welcome to your second lesson on JavaScript objects! In this lesson, we will explore various techniques for manipulating objects, including adding and removing properties, iterating through object properties, and using object methods effectively.

**Adding and Removing Properties:**

**1. Adding Properties:**
You can add properties to an existing object using both dot notation and bracket notation.

```javascript
let person = {
  firstName: "John",
  lastName: "Doe",
};

person.age = 30; // Adding a new property
console.log(person.age); // Output: 30
```

**2. Removing Properties:**
To remove a property from an object, you can use the `delete` operator.

```javascript
delete person.lastName;
console.log(person.lastName); // Output: undefined
```

**Iterating Through Object Properties:**

To loop through all properties in an object, you can use the `for...in` loop.

```javascript
for (let key in person) {
  console.log(key + ": " + person[key]);
}
```

**Using Object Methods:**

JavaScript provides built-in methods that allow you to work with objects effectively.

**1. `Object.keys()`:** This method returns an array containing all the keys (properties) of an object.

```javascript
let keys = Object.keys(person);
console.log(keys); // Output: ["firstName", "age"]
```

**2. `Object.values()`:** This method returns an array containing all the values of an object.

```javascript
let values = Object.values(person);
console.log(values); // Output: ["John", 30]
```

**3. `Object.entries()`:** This method returns an array of arrays, where each inner array contains a key-value pair.

```javascript
let entries = Object.entries(person);
console.log(entries); // Output: [["firstName", "John"], ["age", 30]]
```

**Using `this` Keyword:**

When defining methods in an object, you can use the `this` keyword to refer to the object itself. This is particularly useful when you want to access object properties from within a method.

```javascript
let user = {
  firstName: "Alice",
  greet: function() {
    console.log("Hello, " + this.firstName + "!");
  },
};

user.greet(); // Output: Hello, Alice!
```

**Object Cloning:**

You can create a shallow copy of an object using the `Object.assign()` method.

```javascript
let original = { a: 1, b: 2 };
let copy = Object.assign({}, original);
```

**Summary:**

In this lesson, you've learned how to add and remove properties from objects, iterate through object properties using `for...in` loops, and utilize useful object methods like `Object.keys()`, `Object.values()`, and `Object.entries()`. You've also explored the use of the `this` keyword within object methods. Keep practicing these techniques to become proficient in working with JavaScript objects. In the next lesson, we'll delve into more advanced topics, including nested objects and object prototypes.