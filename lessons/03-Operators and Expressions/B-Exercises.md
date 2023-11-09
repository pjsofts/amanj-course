---
title: "Operators and Expressions Exercises"
description: "Operators and Expressions Exercises"
---



## Exercises:

## Exercise 1: Arithmetic Operations
1. Declare two variables, `num1` and `num2`, and assign them any numerical values. Perform the following operations:
   - Addition
   - Subtraction
   - Multiplication
   - Division
   - Modulus

## Exercise 2: Comparison Operations
2. Declare two variables, `val1` and `val2`, and assign them values of different data types. Use comparison operators to check:
   - If they are equal using `==` and `===`
   - If they are not equal using `!=` and `!==`
   - If `val1` is greater than `val2`
   - If `val1` is less than or equal to `val2`

## Exercise 3: Logical Operations
3. Declare three boolean variables, `a`, `b`, and `c`, and assign them values. Use logical operators to evaluate the following expressions:
   - `a && b`
   - `b || c`
   - `!(a && c)`

## Exercise 4: Ternary Operator
4. Write a program that determines whether a given number is even or odd using the ternary operator.

### Homework:

## Homework 1: Expressions Challenge
1. Create a program that calculates the area of a triangle using the formula `area = 0.5 * base * height`. Prompt the user for the base and height.

## Homework 2: Temperature Conversion
2. Write a program that converts temperatures between Celsius and Fahrenheit. Prompt the user for a temperature and the unit (C or F), then perform the conversion.

## Homework 3: Conditional Banking
3. Create a simple banking system. Prompt the user for their account balance. If the balance is greater than 1000, give them a 10% bonus; otherwise, charge them a 5% fee. Display the updated balance.

### Answers:

## Exercise 1: Arithmetic Operations
```javascript
let num1 = 7;
let num2 = 3;

let addition = num1 + num2;
let subtraction = num1 - num2;
let multiplication = num1 * num2;
let division = num1 / num2;
let modulus = num1 % num2;
```

## Exercise 2: Comparison Operations
```javascript
let val1 = 10;
let val2 = '10';

let isEqualDoubleEquals = (val1 == val2);
let isEqualTripleEquals = (val1 === val2);
let isNotEqual = (val1 != val2);
let isNotStrictEqual = (val1 !== val2);
let isGreaterThan = (val1 > val2);
let isLessThanOrEqual = (val1 <= val2);
```

## Exercise 3: Logical Operations
```javascript
let a = true;
let b = false;
let c = true;

let result1 = a && b;
let result2 = b || c;
let result3 = !(a && c);
```

## Exercise 4: Ternary Operator
```javascript
let number = prompt("Enter a number:");
let result = (number % 2 === 0) ? "Even" : "Odd";
console.log(result);
```

