---
title: "Advanced JavaScript Exception Handling"
---

### Lesson 2: Advanced JavaScript Exception Handling

#### 1. Throwing Custom Errors

In addition to built-in error types like `SyntaxError` or `TypeError`, you can create custom error objects to represent specific errors in your code. This allows you to provide more context and information when an exception occurs.

```javascript
class MyCustomError extends Error {
  constructor(message) {
    super(message);
    this.name = 'MyCustomError';
  }
}

try {
  // Code that may throw a custom error
  throw new MyCustomError('Something went wrong!');
} catch (error) {
  if (error instanceof MyCustomError) {
    console.error('Custom error caught:', error.message);
  } else {
    console.error('An unexpected error occurred:', error.message);
  }
}
```

By extending the `Error` class, you can create custom error types with their own names and messages, making it easier to identify and handle them.

#### 2. Multiple `catch` Blocks

You can have multiple `catch` blocks to handle different types of exceptions. JavaScript will execute the first `catch` block that matches the exception type.

```javascript
try {
  // Code that may throw an error
} catch (syntaxError) {
  console.error('Syntax error:', syntaxError.message);
} catch (referenceError) {
  console.error('Reference error:', referenceError.message);
} catch (error) {
  console.error('An unexpected error occurred:', error.message);
}
```

Having multiple `catch` blocks allows you to handle specific types of errors differently.

#### 3. Rethrowing Exceptions

Sometimes, you may want to catch an exception, perform some logging or cleanup, and then rethrow the same exception to propagate it up the call stack for further handling.

```javascript
try {
  // Code that may throw an error
} catch (error) {
  console.error('An error occurred:', error.message);
  // Perform cleanup or additional handling
  throw error; // Rethrow the same error
}
```

Rethrowing an exception can be useful for logging or taking specific actions while ensuring that the original exception isn't lost.

#### 4. Error Propagation

When you encounter an exception you can't handle at a particular level, it's often better to let it propagate up the call stack to a higher-level error handler.

```javascript
function innerFunction() {
  throw new Error('Inner function error');
}

function outerFunction() {
  try {
    innerFunction();
  } catch (error) {
    console.error('Caught an error:', error.message);
    // Don't rethrow; let it propagate to a higher-level handler
  }
}

outerFunction();
```

In this example, the `innerFunction` throws an error, which is caught by the `outerFunction`. The `outerFunction` logs the error but doesn't rethrow it, allowing it to continue propagating.

#### 5. Async/Await Error Handling

When working with asynchronous code using `async/await`, you can handle errors using try-catch blocks just like with synchronous code.

```javascript
async function fetchData() {
  try {
    const response = await fetch('https://api.example.com/data');
    const data = await response.json();
    return data;
  } catch (error) {
    console.error('Error fetching data:', error.message);
    throw error; // Rethrow if necessary
  }
}
```

Handling errors in asynchronous code ensures that your application remains stable even when network requests or asynchronous operations fail.

#### 6. Error Logging and Reporting

In real-world applications, it's essential to log and report errors for debugging and monitoring purposes. You can use logging libraries like `console.error`, `console.log`, or dedicated error tracking services to collect and analyze error data in production.

#### 7. Graceful Degradation

In some cases, you can design your code to gracefully handle errors and continue functioning, providing fallbacks or alternative paths when errors occur. This approach can improve the user experience.

```javascript
function safeDivision(a, b) {
  try {
    if (b === 0) {
      throw new Error('Division by zero');
    }
    return a / b;
  } catch (error) {
    console.error('Error:', error.message);
    return Infinity; // Provide a fallback value
  }
}
```

By considering how your code handles errors, you can ensure that your application remains stable and provides informative feedback to users.

In this lesson, you've explored advanced JavaScript exception handling techniques and best practices. Effective exception handling is crucial for creating robust and reliable applications, and mastering these techniques will make you a more proficient developer.