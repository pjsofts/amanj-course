---
title: "Introduction to JavaScript Objects"
---

**Lesson 1: Introduction to JavaScript Objects**

Welcome to your first lesson on JavaScript objects! Objects are fundamental data structures in JavaScript that allow you to store and organize related data and functions. They are a crucial concept in modern programming, enabling you to create complex and dynamic applications.

**What is an Object?**
An object is a collection of key-value pairs where each value can be of any data type: strings, numbers, arrays, other objects, functions, and more. Think of an object as a container that holds related information together. The keys in an object are also called properties, and they are used to access the corresponding values.

**Creating an Object:**
You can create an object in JavaScript using two main methods: object literal notation and the `Object` constructor.

**1. Object Literal Notation:**
```javascript
// Creating an empty object
let person = {};

// Adding properties to the object
person.firstName = "John";
person.lastName = "Doe";
person.age = 30;

// Accessing properties
console.log(person.firstName); // Output: John
console.log(person.age);       // Output: 30
```

**2. Using the Object Constructor:**
```javascript
// Creating an object using the constructor
let car = new Object();

// Adding properties to the object
car.make = "Toyota";
car.model = "Camry";
car.year = 2023;

// Accessing properties
console.log(car.make);  // Output: Toyota
console.log(car.year);  // Output: 2023
```

**Object Literal Notation vs. Object Constructor:**
Both methods achieve the same result, but object literal notation is more commonly used due to its simplicity and readability.

**Accessing Object Properties:**
You can access object properties using dot notation or bracket notation.

```javascript
// Using dot notation
console.log(person.firstName); // Output: John

// Using bracket notation (especially useful when property names have spaces or special characters)
console.log(person['lastName']); // Output: Doe
```

**Methods in Objects:**
Objects can also contain functions as properties, which are called methods. Methods allow you to perform actions or calculations related to the object.

```javascript
let calculator = {
  add: function(a, b) {
    return a + b;
  },
  subtract: function(a, b) {
    return a - b;
  }
};

console.log(calculator.add(5, 3));      // Output: 8
console.log(calculator.subtract(10, 4)); // Output: 6
```

In this lesson, you've learned the basics of JavaScript objects, including creating objects, adding properties, accessing properties, and including methods. Objects are the building blocks for more advanced programming concepts, so mastering them is essential for becoming proficient in JavaScript. Stay tuned for the next lesson, where we'll dive deeper into manipulating and working with objects!