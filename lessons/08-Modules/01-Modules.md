---
title: "Creating and Using JavaScript Modules"
---

### Lesson 1: Creating and Using JavaScript Modules

#### What is a Module?

A JavaScript module is a self-contained unit of code that encapsulates a specific functionality or feature. It can include variables, functions, classes, or even objects, all organized in a way that makes it easy to import and use in other parts of your codebase.

#### Creating a Module

To create a JavaScript module, you typically create a separate `.js` file for each module. Here's a simple example of a module that defines some utility functions:

```javascript
// utils.js
export function add(a, b) {
  return a + b;
}

export function subtract(a, b) {
  return a - b;
}
```

In this example, we have defined two functions (`add` and `subtract`) in the `utils.js` module, and we've used the `export` keyword to make these functions available for use in other modules.

#### Importing a Module

To use the functions from the `utils.js` module in another JavaScript file, you can use the `import` statement. Here's how you can import and use the functions:

```javascript
// main.js
import { add, subtract } from './utils.js';

const result1 = add(5, 3);
const result2 = subtract(10, 4);

console.log(result1); // Output: 8
console.log(result2); // Output: 6
```

In this example, we import the `add` and `subtract` functions from the `utils.js` module and use them in the `main.js` file.

#### Default Exports

In addition to named exports (like `add` and `subtract` in the example above), you can also use default exports to export a single value from a module. Here's an example:

```javascript
// math.js
const pi = 3.14159265359;

export default pi;
```

To import the default export, you can use the following syntax:

```javascript
// main.js
import pi from './math.js';

console.log(pi); // Output: 3.14159265359
```

#### CommonJS Modules

In addition to the ES6 module system shown above, JavaScript also supports the CommonJS module system, which is used in Node.js and in some older front-end projects. CommonJS uses `require` and `module.exports` to define and import modules. Here's a simple example:

```javascript
// utils.js using CommonJS
function add(a, b) {
  return a + b;
}

function subtract(a, b) {
  return a - b;
}

module.exports = {
  add,
  subtract,
};
```

```javascript
// main.js using CommonJS
const { add, subtract } = require('./utils.js');

const result1 = add(5, 3);
const result2 = subtract(10, 4);

console.log(result1); // Output: 8
console.log(result2); // Output: 6
```

#### Browser Support

Keep in mind that ES6 modules (the `import` and `export` syntax) are well-supported in modern browsers. However, if you need to support older browsers or are working in a Node.js environment, you may still encounter CommonJS modules.

In this lesson, you've learned the basics of creating and using JavaScript modules. Modules help you organize your code and make it more maintainable. In the next lessons, we'll dive deeper into module features and best practices.