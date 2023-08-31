---
title: "Function Exercises"
---

**Exercise 1: Calculate the Factorial**
Write a function that calculates the factorial of a given positive integer.

```javascript
function factorial(n) {
    if (n === 0 || n === 1) {
        return 1;
    } else {
        return n * factorial(n - 1);
    }
}

console.log(factorial(5)); // Output: 120
```

**Exercise 2: Find the Longest Word**
Write a function that takes an array of words and returns the longest word in the array.

```javascript
function findLongestWord(words) {
    let longestWord = "";

    for (const word of words) {
        if (word.length > longestWord.length) {
            longestWord = word;
        }
    }

    return longestWord;
}

const wordArray = ["apple", "banana", "cherry", "date"];
console.log(findLongestWord(wordArray)); // Output: banana
```

**Exercise 3: Palindrome Checker**
Write a function that checks if a given string is a palindrome (reads the same forwards and backwards).

```javascript
function isPalindrome(str) {
    const cleanedStr = str.toLowerCase().replace(/[^a-z0-9]/g, "");
    const reversedStr = cleanedStr.split("").reverse().join("");
    return cleanedStr === reversedStr;
}

console.log(isPalindrome("racecar")); // Output: true
console.log(isPalindrome("hello"));   // Output: false
```

**Exercise 4: Fibonacci Series**
Write a function that generates the first `n` numbers of the Fibonacci sequence.

```javascript
function fibonacci(n) {
    const sequence = [0, 1];

    for (let i = 2; i < n; i++) {
        sequence.push(sequence[i - 1] + sequence[i - 2]);
    }

    return sequence;
}

console.log(fibonacci(8)); // Output: [0, 1, 1, 2, 3, 5, 8, 13]
```

**Exercise 5: Title Case a Sentence**
Write a function that converts a sentence to title case (capitalize the first letter of each word).

```javascript
function titleCase(sentence) {
    const words = sentence.toLowerCase().split(" ");
    const titleCaseWords = words.map(word => word.charAt(0).toUpperCase() + word.slice(1));
    return titleCaseWords.join(" ");
}

console.log(titleCase("hello world")); // Output: Hello World
```

