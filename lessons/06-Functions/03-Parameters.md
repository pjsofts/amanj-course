---
title: "Function Parameters, Arguments, and Return Values"
---

**Lesson 3: Function Parameters, Arguments, and Return Values**

In this lesson, we'll explore more about function parameters, arguments, and return values in JavaScript.

**1. Default Parameters (ES6):**
You can provide default values for function parameters. If an argument isn't passed when the function is called or if it's `undefined`, the default value will be used.

```javascript
function greet(name = "Guest") {
    console.log("Hello, " + name + "!");
}

greet();          // Output: Hello, Guest!
greet("Alice");   // Output: Hello, Alice!
```

**2. Rest Parameters (ES6):**
The rest parameter allows you to pass a variable number of arguments to a function as an array. It's denoted by `...` followed by the parameter name.

```javascript
function sum(...numbers) {
    return numbers.reduce((total, num) => total + num, 0);
}

console.log(sum(1, 2, 3)); // Output: 6
console.log(sum(4, 5));    // Output: 9
```

**3. Arguments Object:**
Inside a function, you can access all the passed arguments using the `arguments` object, even if they aren't explicitly defined as parameters.

```javascript
function showArgs() {
    for (let i = 0; i < arguments.length; i++) {
        console.log(arguments[i]);
    }
}

showArgs(1, "hello", true); // Output: 1, hello, true
```

**4. Returning Values:**
Functions can return values using the `return` statement. When a function encounters a `return`, it stops executing and passes the specified value back to the caller.

```javascript
function multiply(a, b) {
    return a * b;
}

const result = multiply(3, 4);
console.log(result); // Output: 12
```

**5. Returning Multiple Values:**
In JavaScript, you can return multiple values from a function by using an object, an array, or more recently, destructuring (ES6).

```javascript
function getPerson() {
    return { firstName: "John", lastName: "Doe" };
}

const person = getPerson();
console.log(person.firstName); // Output: John

function getCoordinates() {
    return [12.345, 67.890];
}

const [latitude, longitude] = getCoordinates();
console.log(latitude, longitude); // Output: 12.345 67.890
```

**6. Callback Functions:**
Functions can be passed as arguments to other functions, which are then called within the receiving function. These are known as callback functions and are often used for asynchronous tasks.

```javascript
function doSomething(callback) {
    console.log("Doing something...");
    callback();
}

function afterSomething() {
    console.log("After something.");
}

doSomething(afterSomething);
```

These are important concepts regarding function parameters, arguments, and return values in JavaScript. Understanding how to pass and manipulate data between functions is essential for creating more complex and efficient programs.