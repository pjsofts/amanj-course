---
title: "Object Exercises"
---

**Exercise 1:**
Create an object named `person` with properties `name`, `age`, and `job`.

**Answer:**
```javascript
let person = {
  name: "John",
  age: 30,
  job: "Engineer"
};
```

**Exercise 2:**
Add a method `getDetails` to the `person` object that returns a string with all the details.

**Answer:**
```javascript
person.getDetails = function() {
  return `${this.name} is ${this.age} years old and works as a ${this.job}.`;
};
```

**Exercise 3:**
Create a nested object `address` inside the `person` object with properties `street`, `city`, and `zipcode`.

**Answer:**
```javascript
person.address = {
  street: "123 Main St",
  city: "Cityville",
  zipcode: "12345"
};
```

**Exercise 4:**
Loop through the properties of the `person` object and log each property and its value.

**Answer:**
```javascript
for (let key in person) {
  console.log(`${key}: ${person[key]}`);
}
```

**Exercise 5:**
Create a constructor function `Student` that takes `name` and `grade` as parameters and creates an object with those properties.

**Answer:**
```javascript
function Student(name, grade) {
  this.name = name;
  this.grade = grade;
}

let student1 = new Student("Alice", 10);
let student2 = new Student("Bob", 8);
```

**Exercise 6:**
Add a method `getGrade` to the `Student` constructor that returns the student's grade.

**Answer:**
```javascript
Student.prototype.getGrade = function() {
  return `${this.name} is in grade ${this.grade}.`;
};
```

**Exercise 7:**
Create a class `Rectangle` with properties `width` and `height` and a method `getArea` that returns the area.

**Answer:**
```javascript
class Rectangle {
  constructor(width, height) {
    this.width = width;
    this.height = height;
  }
  
  getArea() {
    return this.width * this.height;
  }
}

let rect = new Rectangle(5, 10);
console.log(rect.getArea()); // Output: 50
```

**Exercise 8:**
Create a function `mergeObjects` that takes two objects and returns a new object with properties from both.

**Answer:**
```javascript
function mergeObjects(obj1, obj2) {
  return { ...obj1, ...obj2 };
}

let object1 = { a: 1, b: 2 };
let object2 = { b: 3, c: 4 };
let merged = mergeObjects(object1, object2);
console.log(merged); // Output: { a: 1, b: 3, c: 4 }
```

**Exercise 9:**
Create an object `circle` with a property `radius`. Add methods `getArea` and `getCircumference`.

**Answer:**
```javascript
let circle = {
  radius: 5,
  getArea: function() {
    return Math.PI * this.radius ** 2;
  },
  getCircumference: function() {
    return 2 * Math.PI * this.radius;
  }
};
```

**Exercise 10:**
Create a function `countProperties` that takes an object and returns the number of properties it has.

**Answer:**
```javascript
function countProperties(obj) {
  return Object.keys(obj).length;
}

let object = { a: 1, b: 2, c: 3 };
console.log(countProperties(object)); // Output: 3
```

**Exercise 11:**
Create an object `inventory` with properties for different items and their quantities.

**Answer:**
```javascript
let inventory = {
  apples: 10,
  bananas: 20,
  oranges: 15
};
```

**Exercise 12:**
Write a function `isPersonEqual` that takes two person objects and checks if they have the same properties and values.

**Answer:**
```javascript
function isPersonEqual(person1, person2) {
  return JSON.stringify(person1) === JSON.stringify(person2);
}

let person1 = { name: "John", age: 30 };
let person2 = { name: "John", age: 30 };
console.log(isPersonEqual(person1, person2)); // Output: true
```

**Exercise 13:**
Create an object `book` with properties `title` and `author`. Use a setter method to change the author.

**Answer:**
```javascript
let book = {
  title: "The Great Gatsby",
  _author: "F. Scott Fitzgerald",
  set author(newAuthor) {
    this._author = newAuthor;
  },
  get author() {
    return this._author;
  }
};

book.author = "Jane Austen";
console.log(book.author); // Output: Jane Austen
```

**Exercise 14:**
Create an object `playlist` that stores a list of songs. Add methods to add, remove, and get songs.

**Answer:**
```javascript
let playlist = {
  songs: [],
  addSong: function(song) {
    this.songs.push(song);
  },
  removeSong: function(song) {
    let index = this.songs.indexOf(song);
    if (index !== -1) {
      this.songs.splice(index, 1);
    }
  },
  getSongs: function() {
    return this.songs;
  }
};

playlist.addSong("Song 1");
playlist.addSong("Song 2");
console.log(playlist.getSongs()); // Output: ["Song 1", "Song 2"]
playlist.removeSong("Song 1");
console.log(playlist.getSongs()); // Output: ["Song 2"]
```

**Exercise 15:**
Create a class `Employee` with properties `name` and `salary`. Create a method that increases the salary.

**Answer:**
```javascript
class Employee {
  constructor(name, salary) {
    this.name = name;
    this.salary = salary;
  }
  
  increaseSalary(amount) {
    this.salary += amount;
  }
}

let employee = new Employee("Alice", 50000);
employee.increaseSalary(5000);
console.log(employee.salary); // Output: 55000
```

**Exercise 16:**
Create a class `BankAccount` with properties `balance` and methods to deposit and withdraw money.

**Answer:**
```javascript
class BankAccount {
  constructor(initialBalance) {
    this.balance = initialBalance;
  }
  
  deposit(amount) {
    this.balance += amount;
  }
  
  withdraw(amount) {
    if (this.balance >= amount) {
      this.balance -= amount;
    } else {
      console.log("Insufficient balance.");
    }
  }
}

let account = new BankAccount(1000);
account.deposit(500);
account.withdraw(300);
console.log(account.balance); // Output: 1200
```

**Exercise 17:**
Create a function `findDuplicates` that takes an array and returns an object with duplicate values as

 keys and their counts as values.

**Answer:**
```javascript
function findDuplicates(arr) {
  let duplicates = {};
  for (let item of arr) {
    if (duplicates[item]) {
      duplicates[item]++;
    } else {
      duplicates[item] = 1;
    }
  }
  return duplicates;
}

let numbers = [1, 2, 3, 2, 4, 3, 5, 6, 1];
console.log(findDuplicates(numbers)); // Output: { 2: 2, 3: 2, 1: 2 }
```

**Exercise 18:**
Create a class `Person` with properties `name` and `age`. Create a method that returns if the person is an adult (age >= 18).

**Answer:**
```javascript
class Person {
  constructor(name, age) {
    this.name = name;
    this.age = age;
  }
  
  isAdult() {
    return this.age >= 18;
  }
}

let person = new Person("John", 25);
console.log(person.isAdult()); // Output: true
```

**Exercise 19:**
Create an object `weather` with properties `temperature` and `conditions`. Add a method that provides a weather report.

**Answer:**
```javascript
let weather = {
  temperature: 75,
  conditions: "sunny",
  getWeatherReport: function() {
    return `The weather is ${this.conditions} with a temperature of ${this.temperature} degrees.`;
  }
};

console.log(weather.getWeatherReport()); // Output: The weather is sunny with a temperature of 75 degrees.
```

**Exercise 20:**
Create a class `Product` with properties `name`, `price`, and `quantity`. Add a method to calculate the total cost.

**Answer:**
```javascript
class Product {
  constructor(name, price, quantity) {
    this.name = name;
    this.price = price;
    this.quantity = quantity;
  }
  
  getTotalCost() {
    return this.price * this.quantity;
  }
}

let product = new Product("Widget", 10, 5);
console.log(product.getTotalCost()); // Output: 50
```

Feel free to practice and modify these exercises to deepen your understanding of JavaScript objects. If you have any questions or need further explanations, don't hesitate to ask!