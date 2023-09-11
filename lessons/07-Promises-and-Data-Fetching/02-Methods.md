---
title: "Promise Methods and Error Handling"
---

**Lesson 2: Promise Methods and Error Handling**

In the previous lesson, we introduced Promises and showed you the basics of using them for data fetching. In this lesson, we will explore some common Promise methods and more advanced error handling techniques.

**1. Promise Methods:**

Promises come with a set of methods that make working with asynchronous code more convenient.

- **`Promise.all()`**: This method takes an array of Promises and returns a single Promise that fulfills when all the Promises in the array fulfill or rejects when any one of them rejects. It's useful for parallel operations.

  ```javascript
  const promise1 = fetch('https://api.example.com/data1');
  const promise2 = fetch('https://api.example.com/data2');

  Promise.all([promise1, promise2])
    .then(responses => {
      // Handle the responses from both requests
      const data1 = responses[0].json();
      const data2 = responses[1].json();
      return Promise.all([data1, data2]);
    })
    .then(data => {
      // Work with the combined data
      console.log(data[0], data[1]);
    })
    .catch(error => {
      // Handle errors from any of the Promises
      console.error('Promise.all error:', error);
    });
  ```

- **`Promise.race()`**: This method takes an array of Promises and returns a new Promise that fulfills or rejects as soon as one of the Promises in the array does. It's useful for scenarios where you want the result of the first responding Promise.

  ```javascript
  const promise1 = fetch('https://api.example.com/data1');
  const promise2 = fetch('https://api.example.com/data2');

  Promise.race([promise1, promise2])
    .then(response => {
      // Handle the response from the first successful request
      console.log(response);
    })
    .catch(error => {
      // Handle errors from the first rejecting Promise
      console.error('Promise.race error:', error);
    });
  ```

**2. Error Handling:**

Error handling is a critical aspect of asynchronous code. In addition to using `.catch()` as shown earlier, you can also handle errors inside individual `.then()` blocks by returning a rejected Promise using `Promise.reject()`.

```javascript
fetch('https://api.example.com/data')
  .then(response => {
    if (!response.ok) {
      return Promise.reject('Network response was not ok');
    }
    return response.json();
  })
  .then(data => {
    // Work with the fetched data
    console.log(data);
  })
  .catch(error => {
    // Handle errors here
    console.error('Fetch error:', error);
  });
```

**3. Async/Await:**

While Promises provide a powerful way to work with asynchronous code, modern JavaScript also introduced the `async/await` syntax, which makes asynchronous code look more like synchronous code. Here's how you can rewrite the previous example using `async/await`:

```javascript
async function fetchData() {
  try {
    const response = await fetch('https://api.example.com/data');
    
    if (!response.ok) {
      throw new Error('Network response was not ok');
    }

    const data = await response.json();
    // Work with the fetched data
    console.log(data);
  } catch (error) {
    // Handle errors here
    console.error('Fetch error:', error);
  }
}

fetchData();
```

`async/await` simplifies the syntax and makes it easier to read and write asynchronous code.

That concludes the second lesson on JavaScript data fetching and Promises, covering Promise methods and error handling techniques. In the next lesson, we'll explore more advanced topics such as handling multiple asynchronous operations and managing complex data flows.