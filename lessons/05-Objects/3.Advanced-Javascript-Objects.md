---
title: "Advanced JavaScript Objects"
---

**Lesson 3: Advanced JavaScript Objects**

Welcome to your third lesson on JavaScript objects! In this lesson, we'll dive into more advanced concepts related to objects, including working with nested objects, object prototypes, and object constructors.

**Nested Objects:**

Objects can contain other objects as their properties. These are called nested objects and are useful for representing complex data structures.

```javascript
let person = {
  name: {
    firstName: "John",
    lastName: "Doe",
  },
  age: 30,
};

console.log(person.name.firstName); // Output: John
```

**Object Prototypes:**

JavaScript is a prototype-based language, which means objects can inherit properties and methods from other objects called prototypes.

```javascript
// Creating a prototype object
let animal = {
  speak: function() {
    console.log("Some sound");
  },
};

// Creating an object that inherits from the prototype
let dog = Object.create(animal);
dog.speak(); // Output: Some sound
```

**Constructor Functions:**

Constructor functions are used to create multiple objects with similar properties and methods. They're commonly used for object templates.

```javascript
function Car(make, model, year) {
  this.make = make;
  this.model = model;
  this.year = year;
}

let myCar = new Car("Toyota", "Camry", 2023);
console.log(myCar.make); // Output: Toyota
```

**Adding Methods to Prototypes:**

To avoid duplicating methods across instances, you can add methods to the prototype of a constructor function.

```javascript
Car.prototype.start = function() {
  console.log("Engine started");
};

myCar.start(); // Output: Engine started
```

**Class Syntax (ES6):**

ES6 introduced the `class` syntax, which provides a more structured way to define constructor functions and their methods.

```javascript
class Book {
  constructor(title, author) {
    this.title = title;
    this.author = author;
  }

  getInfo() {
    return `${this.title} by ${this.author}`;
  }
}

let myBook = new Book("The Great Gatsby", "F. Scott Fitzgerald");
console.log(myBook.getInfo()); // Output: The Great Gatsby by F. Scott Fitzgerald
```

**Inheritance and Super (ES6):**

With ES6 classes, you can easily implement inheritance and use the `super` keyword to call methods from the parent class.

```javascript
class SportsCar extends Car {
  constructor(make, model, year, topSpeed) {
    super(make, model, year);
    this.topSpeed = topSpeed;
  }
}

let mySportsCar = new SportsCar("Ferrari", "488", 2023, 210);
console.log(mySportsCar.start()); // Output: Engine started
console.log(mySportsCar.topSpeed); // Output: 210
```

**Summary:**

In this lesson, you've explored advanced concepts related to JavaScript objects. You've learned about nested objects, object prototypes, constructor functions, the `class` syntax, and inheritance. These concepts are crucial for building more complex and organized applications. Continue practicing and experimenting with objects to solidify your understanding. In the next lesson, we'll cover JSON (JavaScript Object Notation) and how to convert objects to JSON and vice versa.