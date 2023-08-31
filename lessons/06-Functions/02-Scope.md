---
title: "Function Scope and Hoisting in JavaScript"
---

**Lesson 2: Function Scope and Hoisting in JavaScript**

In this lesson, we'll dive deeper into the concepts of function scope and hoisting in JavaScript. Understanding these concepts is crucial for writing reliable and predictable code.

**1. Function Scope:**
Variables declared inside a function are said to have function scope. This means they are only accessible within that function. Variables declared outside any function have global scope, making them accessible throughout the entire script.

```javascript
function myFunction() {
    const localVar = "I'm local!";
    console.log(localVar); // Output: I'm local!
}

myFunction();
console.log(localVar); // Error: localVar is not defined
```

**2. Hoisting:**
JavaScript "hoists" variable and function declarations to the top of their containing scope during compilation, regardless of where they're defined. However, only the declarations are hoisted, not the assignments. This can lead to unexpected behavior if not understood properly.

```javascript
console.log(myVar); // Output: undefined
var myVar = 42;

hoistedFunction(); // Output: "Hello, hoisting!"
function hoistedFunction() {
    console.log("Hello, hoisting!");
}
```

**3. Function Declarations vs. Function Expressions:**
Function declarations are entirely hoisted, so you can call them before their actual declaration in the code. Function expressions, on the other hand, are only partially hoisted. The variable declaration is hoisted, but the function assignment isn't.

```javascript
declarationFunction(); // Output: "This is a function declaration."
function declarationFunction() {
    console.log("This is a function declaration.");
}

expressionFunction(); // Error: expressionFunction is not a function
var expressionFunction = function() {
    console.log("This is a function expression.");
};
```

**4. Block Scope (ES6):**
Before ES6, JavaScript only had function and global scope. With ES6, the `let` and `const` keywords introduced block scope, making variables confined to the block in which they're defined.

```javascript
if (true) {
    var blockVar = "I'm a block-scoped var.";
    let blockLet = "I'm a block-scoped let.";
}

console.log(blockVar); // Output: I'm a block-scoped var.
console.log(blockLet); // Error: blockLet is not defined
```

**5. Lexical Scope:**
Lexical scope means that functions are executed using the variable scope that was in effect when they were defined, not the scope they are executed in.

```javascript
const outer = () => {
    const localVar = "I'm from outer.";
    
    const inner = () => {
        console.log(localVar); // Output: I'm from outer.
    };
    
    return inner;
};

const innerFunction = outer();
innerFunction();
```

These are the key concepts related to function scope and hoisting in JavaScript. Properly understanding and managing scope and hoisting is crucial for writing code that behaves predictably and avoids bugs.