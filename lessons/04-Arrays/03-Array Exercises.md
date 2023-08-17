Exercise 1: Sum of Array Elements
Write a function that calculates the sum of all elements in an array.

```javascript
function sumArray(arr) {
  let sum = 0;
  for (let i = 0; i < arr.length; i++) {
    sum += arr[i];
  }
  return sum;
}

let numbers = [1, 2, 3, 4, 5];
console.log(sumArray(numbers)); // Should output: 15
```

Exercise 2: Finding Even Numbers

Write a function that returns an array containing only the even numbers from a given array.

```javascript
function getEvenNumbers(arr) {
  return arr.filter(function(number) {
    return number % 2 === 0;
  });
}

let numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];
console.log(getEvenNumbers(numbers)); // Should output: [2, 4, 6, 8, 10]
```

Exercise 3: Reversing an Array
Write a function that reverses the elements in an array without using the built-in `reverse` method.

```javascript
function reverseArray(arr) {
  let reversed = [];
  for (let i = arr.length - 1; i >= 0; i--) {
    reversed.push(arr[i]);
  }
  return reversed;
}

let numbers = [1, 2, 3, 4, 5];
console.log(reverseArray(numbers)); // Should output: [5, 4, 3, 2, 1]
```

Exercise 4: Flattening a Multidimensional Array
Write a function that takes a multidimensional array and returns a flattened version of it.

```javascript
function flattenArray(arr) {
  return arr.reduce(function(flat, subArray) {
    return flat.concat(subArray);
  }, []);
}

let matrix = [
  [1, 2, 3],
  [4, 5, 6],
  [7, 8, 9]
];
console.log(flattenArray(matrix)); // Should output: [1, 2, 3, 4, 5, 6, 7, 8, 9]
```

Exercise 5: Array Duplicates
Write a function that finds and returns any duplicate elements in an array.

```javascript
function findDuplicates(arr) {
  let duplicates = [];
  let seen = {};

  for (let i = 0; i < arr.length; i++) {
    if (seen[arr[i]]) {
      duplicates.push(arr[i]);
    } else {
      seen[arr[i]] = true;
    }
  }

  return duplicates;
}

let numbers = [1, 2, 3, 4, 3, 2, 5, 6, 7, 8, 9, 9];
console.log(findDuplicates(numbers)); // Should output: [2, 3, 9]
```

