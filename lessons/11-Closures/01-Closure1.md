---
title: "Introduction to Closures"
---

Closures are a fundamental concept in JavaScript, and understanding them is crucial for writing effective and maintainable code. In this first lesson on closures in JavaScript, we'll cover the basics:

## What is a Closure?

In JavaScript, a closure is a function that has access to variables from its outer (enclosing) lexical scope even after that outer function has finished executing. In simpler terms, a closure "closes over" its surrounding scope, allowing it to access and manipulate variables from that scope.

Let's start with a simple example to illustrate the concept:

```javascript
function outer() {
  const outerVar = 10;

  function inner() {
    console.log(outerVar); // inner function can access outerVar
  }

  return inner;
}

const closureFn = outer(); // Assigning the inner function to a variable

closureFn(); // Calling the inner function

```

In this example, we have an `outer` function that contains an `inner` function. The `inner` function can access the `outerVar` variable declared in the `outer` function, even though the `outer` function has already executed and returned. This is the essence of a closure: the `inner` function "closes over" the variables it needs from its containing scope (`outer`), preserving them even after the `outer` function has finished executing.

Here's a breakdown of what happens:

1. `outer` function is defined, and `outerVar` is declared and set to `10`.

2. `inner` function is defined within the `outer` function. It has access to the `outerVar` variable due to closure.

3. The `outer` function returns the `inner` function, but it doesn't execute it yet. Instead, it assigns the `inner` function to the `closureFn` variable.

4. When you call `closureFn()`, it executes the `inner` function, and you see `10` logged to the console. This demonstrates that the `inner` function still has access to `outerVar`, even though `outer` has completed its execution.

## Use Cases for Closures

Closures have several important use cases in JavaScript:

1. **Data Encapsulation and Privacy**: Closures can be used to create private variables and functions, hiding them from the outside world and allowing controlled access.

2. **Function Factories**: Closures are often used to create specialized functions with preset configurations or data. This is particularly useful for creating reusable modules.

3. **Callbacks**: Closures are commonly used in callback functions for handling asynchronous operations, such as AJAX requests or timers.

4. **Partial Application**: Closures can be used for partial application of functions, which means fixing some of a function's arguments ahead of time, creating a new function with reduced arity.

5. **Memoization**: Closures can be used to implement memoization, a technique for caching the results of expensive function calls to improve performance.

Understanding closures is essential for writing clean and efficient JavaScript code. In subsequent lessons, we'll explore more advanced topics related to closures and their practical applications.