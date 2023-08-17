
1. Given a list of integers, find the sum of all elements.
2. Write a program to remove all duplicates from a list of strings.
3. Create a function that takes a list of numbers and returns a new list with only the even numbers.
4. Given two lists, find the common elements between them.
5. Implement a function to merge two sorted lists into a single sorted list.
6. Create a program to find the maximum and minimum values in a list of floats.
7. Write a function that takes a list of strings and returns the longest string in the list.
8. Create a program to count the occurrences of each word in a given sentence using a list.
9. Given a list of names, sort them in alphabetical order.
10. Implement a function that takes a list of numbers and returns a new list with the squared values of each element.
12. Multiply all elements in a list.
13. Insert an element at a specific index in the list.
14. Remove an element from the list by its value.
15. Remove an element from the list by its index.
16. Find the index of the first occurrence of a specific element in the list.
17. Find the index of the last occurrence of a specific element in the list.
18. Reverse a list.
20. Check if a list is empty.



<br>


1. Find the sum of all elements in a list of integers:
```javascript
function findSum(list) {
  return list.reduce((sum, num) => sum + num, 0);
}
```

2. Remove duplicates from a list of strings:
```javascript
function removeDuplicates(list) {
  return Array.from(new Set(list));
}
```

3. Return a new list with only the even numbers:
```javascript
function filterEvenNumbers(list) {
  return list.filter(num => num % 2 === 0);
}
```

4. Find common elements between two lists:
```javascript
function findCommonElements(list1, list2) {
  return list1.filter(item => list2.includes(item));
}
```

5. Merge two sorted lists into a single sorted list:
```javascript
function mergeSortedLists(list1, list2) {
  return [...list1, ...list2].sort((a, b) => a - b);
}
```

6. Find maximum and minimum values in a list of floats:
```javascript
function findMinMaxValues(list) {
  const max = Math.max(...list);
  const min = Math.min(...list);
  return { max, min };
}
```

7. Find the longest string in a list of strings:
```javascript
function findLongestString(list) {
  return list.reduce((longest, current) => current.length > longest.length ? current : longest, '');
}
```

8. Count occurrences of each word in a sentence using a list:
```javascript
function countWordOccurrences(sentence) {
  const words = sentence.split(' ');
  const wordCount = {};
  words.forEach(word => {
    wordCount[word] = (wordCount[word] || 0) + 1;
  });
  return wordCount;
}
```

9. Sort a list of names in alphabetical order:
```javascript
function sortNamesAlphabetically(names) {
  return names.sort();
}
```

10. Return a new list with squared values of each element:
```javascript
function squareList(list) {
  return list.map(num => num * num);
}
```

11. Multiply all elements in a list:
```javascript
function multiplyListElements(list) {
  return list.reduce((product, num) => product * num, 1);
}
```

12. Insert an element at a specific index in the list:
```javascript
function insertAtIndex(list, index, element) {
  list.splice(index, 0, element);
  return list;
}
```

13. Remove an element from the list by its value:
```javascript
function removeByValue(list, value) {
  return list.filter(item => item !== value);
}
```

14. Remove an element from the list by its index:
```javascript
function removeByIndex(list, index) {
  list.splice(index, 1);
  return list;
}
```

15. Find the index of the first occurrence of a specific element:
```javascript
function findFirstIndex(list, element) {
  return list.indexOf(element);
}
```

16. Find the index of the last occurrence of a specific element:
```javascript
function findLastIndex(list, element) {
  return list.lastIndexOf(element);
}
```

17. Reverse a list:
```javascript
function reverseList(list) {
  return list.reverse();
}
```

18. Check if a list is empty:
```javascript
function isListEmpty(list) {
  return list.length === 0;
}
```
