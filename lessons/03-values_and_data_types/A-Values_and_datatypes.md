---
title: "Values and Data Types"
description: "Javascript Basic Datatypes"
---
In JavaScript, variables are used to store data values. Each variable has a name, which is used to reference the stored value, and a data type, which defines the type of data that the variable can hold. JavaScript supports several data types, each with its own characteristics and uses. 

Let's go through some common data types with code examples:


1. **Numbers**: Used for storing numeric values.

```javascript
let age = 25; // Integer
let price = 99.99; // Floating-point number
```

2. **Strings**: Used for storing text.

```javascript
let name = "John"; // Double or single quotes can be used
let message = 'Hello, world!';
```

3. **Booleans**: Used for storing true or false values.

```javascript
let isLogged = true;
let hasPermission = false;
```

4. **Null**: Represents the intentional absence of any value.

```javascript
let myVar = null;
```

5. **Undefined**: Represents an uninitialized variable or a missing value.

```javascript
let myVar;
console.log(myVar); // Outputs: undefined
```

6. **Objects**: Used for storing collections of key-value pairs.

```javascript
let person = {
    firstName: "Alice",
    lastName: "Johnson",
    age: 30
};
```

7. **Arrays**: Used for storing ordered collections of values.

```javascript
let colors = ["red", "green", "blue"];
```

8. **Functions**: Used for storing reusable blocks of code.

```javascript
function add(a, b) {
    return a + b;
}
```

9. **Symbols** (ES6): Used to create unique identifiers.

```javascript
let id = Symbol("uniqueID");
```

10. **BigInt** (ES11): Used for working with large integers.

```javascript
let bigValue = 1234567890123456789012345678901234567890n;
```

Now, let's see some variable examples:

```javascript
// Variable declaration and assignment
let age = 30;
let name = "Alice";
let isLoggedIn = true;

// Variable reassignment
age = 31;
name = "Bob";
isLoggedIn = false;

// Using variables in expressions
let total = age + 10;
let greeting = "Hello, " + name + "!";
```

