---
title: "Interesting Object Exercises "
---

**Question 1: Write a JavaScript function to count the occurrences of each word in a given sentence.**

```javascript
function countWordOccurrences(sentence) {
  const words = sentence.toLowerCase().split(/\s+/);
  const occurrences = {};

  for (const word of words) {
    occurrences[word] = (occurrences[word] || 0) + 1;
  }

  return occurrences;
}

const sentence = "This is a test sentence. This is only a test.";
console.log(countWordOccurrences(sentence));
```

**Question 2: Given a list of student names and their corresponding scores, write a function to find the student with the highest score.**

```javascript
function findTopStudent(students) {
  let topStudent = null;
  let highestScore = -1;

  for (const student of students) {
    if (student.score > highestScore) {
      highestScore = student.score;
      topStudent = student;
    }
  }

  return topStudent;
}

const studentList = [
  { name: "Alice", score: 85 },
  { name: "Bob", score: 92 },
  { name: "Charlie", score: 78 }
];

console.log(findTopStudent(studentList));
```

**Question 3: Write a program to check if two strings are anagrams or not (contain the same characters with the same frequency).**

```javascript
function areAnagrams(str1, str2) {
  const sortedStr1 = str1.split("").sort().join("");
  const sortedStr2 = str2.split("").sort().join("");
  return sortedStr1 === sortedStr2;
}

const string1 = "listen";
const string2 = "silent";

console.log(areAnagrams(string1, string2));
```

**Question 4: Create a function that takes a list of numbers as input and returns the frequency of each unique number in the list.**

```javascript
function countNumberFrequency(numbers) {
  const frequency = {};

  for (const num of numbers) {
    frequency[num] = (frequency[num] || 0) + 1;
  }

  return frequency;
}

const numberList = [1, 2, 3, 2, 4, 1, 5, 2, 3, 4];
console.log(countNumberFrequency(numberList));
```

**Question 5: Given a list of book titles and their authors, write a function to search for books written by a specific author.**

```javascript
function findBooksByAuthor(books, author) {
  return books.filter(book => book.author === author);
}

const bookList = [
  { title: "Book 1", author: "Author A" },
  { title: "Book 2", author: "Author B" },
  { title: "Book 3", author: "Author A" }
];

console.log(findBooksByAuthor(bookList, "Author A"));
```

**Question 6: Write a program to find the common elements between two lists.**

```javascript
function findCommonElements(list1, list2) {
  return list1.filter(item => list2.includes(item));
}

const listA = [1, 2, 3, 4, 5];
const listB = [3, 4, 5, 6, 7];

console.log(findCommonElements(listA, listB));
```

**Question 7: Create a function that takes a list of names as input and groups them based on the first letter of each name.**

```javascript
function groupNamesByFirstLetter(names) {
  const groups = {};

  for (const name of names) {
    const firstLetter = name.charAt(0).toUpperCase();

    if (!groups[firstLetter]) {
      groups[firstLetter] = [];
    }

    groups[firstLetter].push(name);
  }

  return groups;
}

const nameList = ["Alice", "Bob", "Charlie", "Diana", "Eva"];
console.log(groupNamesByFirstLetter(nameList));
```

**Question 8: Write a JavaScript function to calculate the average score of a list of students, where each student is represented as an object containing their name and score.**

```javascript
function calculateAverageScore(students) {
  const totalScore = students.reduce((total, student) => total + student.score, 0);
  return totalScore / students.length;
}

const studentList = [
  { name: "Alice", score: 85 },
  { name: "Bob", score: 92 },
  { name: "Charlie", score: 78 }
];

console.log(calculateAverageScore(studentList));
```

**Question 9: Given a list of transactions with payer names and amounts, write a function to calculate the total amount spent by each payer.**

```javascript
function calculateTotalSpent(transactions) {
  const totalSpent = {};

  for (const transaction of transactions) {
    const payer = transaction.payer;
    const amount = transaction.amount;

    totalSpent[payer] = (totalSpent[payer] || 0) + amount;
  }

  return totalSpent;
}

const transactionList = [
  { payer: "Alice", amount: 20 },
  { payer: "Bob", amount: 30 },
  { payer: "Alice", amount: 15 }
];

console.log(calculateTotalSpent(transactionList));
```

**Question 10: Create a program that reads a paragraph from the user and prints the frequency of each word in the paragraph.**

```javascript
function countWordFrequency(paragraph) {
  const words = paragraph.toLowerCase().split(/\s+/);
  const frequency = {};

  for (const word of words) {
    if (frequency[word]) {
      frequency[word]++;
    } else {
      frequency[word] = 1;
    }
  }

  return frequency;
}

const userParagraph = "This is a sample paragraph. This paragraph is just an example.";
console.log(countWordFrequency(userParagraph));
```
