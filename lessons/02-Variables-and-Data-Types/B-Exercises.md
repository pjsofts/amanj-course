---
title: "Exercises"
description: "Variables and Data Types Exercises"
---

**Exercises:**

1. **Variable Declaration:**
   - Declare a variable named `favoriteNumber` and assign your favorite number to it. Then, log the value to the console.

   ```javascript
   let favoriteNumber = 7;
   console.log("My favorite number is: " + favoriteNumber);
   ```

2. **String Manipulation:**
   - Create two variables, `firstName` and `lastName`, with your first and last names. Combine them to form a full name and log it to the console.

   ```javascript
   let firstName = "John";
   let lastName = "Doe";
   let fullName = firstName + " " + lastName;
   console.log("My full name is: " + fullName);
   ```

3. **Arithmetic Operations:**
   - Calculate the area of a rectangle with a width of 8 units and a height of 5 units. Log the result to the console.

   ```javascript
   let width = 8;
   let height = 5;
   let area = width * height;
   console.log("The area of the rectangle is: " + area);
   ```

4. **Boolean Logic:**
   - Write a program that checks if a user is eligible to vote based on their age. If a user is 18 years or older, log "You can vote!" to the console; otherwise, log "You cannot vote."

   ```javascript
   let userAge = 20;
   if (userAge >= 18) {
     console.log("You can vote!");
   } else {
     console.log("You cannot vote.");
   }
   ```

**Homework:**

1. **Variable Declarations:**
   - Create three variables: `carBrand`, `carModel`, and `carYear`. Assign values to them that represent a car's brand, model, and manufacturing year. Log all three values to the console.

   ```javascript
   let carBrand = "Toyota";
   let carModel = "Camry";
   let carYear = 2022;
   console.log("Car: " + carYear + " " + carBrand + " " + carModel);
   ```

2. **String Operations:**
   - Declare a variable `sentence` and assign it a sentence of your choice. Find the length of the sentence and log it to the console.

   ```javascript
   let sentence = "JavaScript is a powerful programming language.";
   let sentenceLength = sentence.length;
   console.log("The length of the sentence is: " + sentenceLength + " characters.");
   ```

3. **Temperature Conversion:**
   - Write a program to convert a temperature from Celsius to Fahrenheit. Prompt the user for the temperature in Celsius and then display the equivalent temperature in Fahrenheit.

   ```javascript
   let celsiusTemperature = prompt("Enter temperature in Celsius:");
   let fahrenheitTemperature = (celsiusTemperature * 9/5) + 32;
   console.log("The temperature in Fahrenheit is: " + fahrenheitTemperature);
   ```

4. **Boolean Logic and Conditions:**
   - Create a program that checks if a user's username and password match a predefined set of credentials. Provide appropriate messages for both correct and incorrect login attempts.

   ```javascript
   let storedUsername = "user123";
   let storedPassword = "password123";

   let enteredUsername = prompt("Enter your username:");
   let enteredPassword = prompt("Enter your password:");

   if (enteredUsername === storedUsername && enteredPassword === storedPassword) {
     console.log("Login successful!");
   } else {
     console.log("Login failed. Please check your credentials.");
   }
   ```

