---
title: "Introduction to JavaScript Functions"
---

**Lesson 1: Introduction to JavaScript Functions**

In JavaScript, functions are essential building blocks for writing modular and reusable code. A function is a block of code designed to perform a specific task or action. By using functions, you can break down your code into smaller, manageable pieces, making it easier to understand, debug, and maintain.

Let's start by learning the basics of creating and using functions in JavaScript.

**1. Defining a Function:**
To define a function in JavaScript, you use the `function` keyword followed by the function name, a pair of parentheses `()`, and a pair of curly braces `{}` to enclose the function's code block. Here's the general syntax:

```javascript
function functionName(parameters) {
    // Function code
}
```

**2. Function Parameters:**
Functions can accept input values called parameters. Parameters are listed within the parentheses when defining the function. They act as placeholders for values that you pass when you call the function. For example:

```javascript
function greet(name) {
    console.log("Hello, " + name + "!");
}
```

In this example, `name` is a parameter that will hold the value you provide when calling the `greet` function.

**3. Calling a Function:**
To execute a function and make it perform its task, you call it by using its name followed by parentheses containing the arguments you want to pass (if any). Arguments are actual values you provide to the function for it to work with. For example:

```javascript
greet("Alice"); // Output: Hello, Alice!
greet("Bob");   // Output: Hello, Bob!
```

**4. Return Statement:**
Functions can also return values using the `return` statement. When a function encounters a `return` statement, it stops executing and immediately returns the specified value. This value can be captured and used when the function is called. For example:

```javascript
function add(a, b) {
    return a + b;
}

let result = add(5, 3);
console.log(result); // Output: 8
```

**5. Function Expression:**
Functions can also be assigned to variables. This is called a function expression. Here's an example:

```javascript
const multiply = function(x, y) {
    return x * y;
};

let product = multiply(4, 7);
console.log(product); // Output: 28
```

**6. Arrow Functions (ES6):**
Arrow functions provide a concise syntax for defining functions, especially when the function body is a single expression. Here's how an arrow function looks:

```javascript
const square = (num) => num * num;

let squared = square(6);
console.log(squared); // Output: 36
```

This concludes the first lesson on JavaScript functions. You've learned how to define functions, pass parameters, call functions, use the `return` statement, and create function expressions and arrow functions. Functions are a fundamental concept in JavaScript programming and are used extensively to organize and structure code.