---
title: "Answers to Promises and Data Fretching Exercises"
---


**Exercise 1: Fetch Data from an API**

```javascript
fetch('https://jsonplaceholder.typicode.com/todos/1')
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```

**Exercise 2: Handle Errors**

```javascript
fetch('https://jsonplaceholder.typicode.com/todos/99999')
  .then(response => {
    if (!response.ok) {
      throw new Error('Network response was not ok');
    }
    return response.json();
  })
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```

**Exercise 3: Chaining Promises**

```javascript
fetch('https://jsonplaceholder.typicode.com/posts/1')
  .then(response => response.json())
  .then(postData => {
    return fetch('https://jsonplaceholder.typicode.com/users/1')
      .then(response => response.json())
      .then(userData => {
        console.log('Post Data:', postData);
        console.log('User Data:', userData);
      });
  })
  .catch(error => console.error('Error:', error));
```

**Exercise 4: Promise.all**

```javascript
const fetchPost = fetch('https://jsonplaceholder.typicode.com/posts/1').then(response => response.json());
const fetchUser = fetch('https://jsonplaceholder.typicode.com/users/1').then(response => response.json());

Promise.all([fetchPost, fetchUser])
  .then(([postData, userData]) => {
    console.log('Post Data:', postData);
    console.log('User Data:', userData);
  })
  .catch(error => console.error('Error:', error));
```

**Exercise 5: Async/Await**

```javascript
async function fetchData() {
  try {
    const response = await fetch('https://jsonplaceholder.typicode.com/todos/1');
    if (!response.ok) {
      throw new Error('Network response was not ok');
    }
    const data = await response.json();
    console.log(data);
  } catch (error) {
    console.error('Error:', error);
  }
}

fetchData();
```

**Exercise 6: Error Handling with Async/Await**

```javascript
async function fetchData() {
  try {
    const response = await fetch('https://jsonplaceholder.typicode.com/todos/99999');
    if (!response.ok) {
      throw new Error('Network response was not ok');
    }
    const data = await response.json();
    console.log(data);
  } catch (error) {
    console.error('Error:', error);
  }
}

fetchData();
```

**Exercise 7: Fetch and Render**

HTML:
```html
<button id="fetchButton">Fetch Data</button>
<div id="output"></div>
```

JavaScript:
```javascript
const fetchButton = document.getElementById('fetchButton');
const outputDiv = document.getElementById('output');

fetchButton.addEventListener('click', () => {
  fetch('https://jsonplaceholder.typicode.com/todos/1')
    .then(response => response.json())
    .then(data => {
      outputDiv.textContent = JSON.stringify(data, null, 2);
    })
    .catch(error => {
      console.error('Error:', error);
      outputDiv.textContent = 'An error occurred.';
    });
});
```

**Exercise 8: Loading Indicator**

HTML:
```html
<button id="fetchButton">Fetch Data</button>
<div id="loadingIndicator" style="display: none;">Loading...</div>
<div id="output"></div>
```

JavaScript:
```javascript
const fetchButton = document.getElementById('fetchButton');
const loadingIndicator = document.getElementById('loadingIndicator');
const outputDiv = document.getElementById('output');

fetchButton.addEventListener('click', () => {
  loadingIndicator.style.display = 'block';

  fetch('https://jsonplaceholder.typicode.com/todos/1')
    .then(response => response.json())
    .then(data => {
      outputDiv.textContent = JSON.stringify(data, null, 2);
    })
    .catch(error => {
      console.error('Error:', error);
      outputDiv.textContent = 'An error occurred.';
    })
    .finally(() => {
      loadingIndicator.style.display = 'none';
    });
});
```

**Exercise 9: Pagination**

HTML:
```html
<button id="prevButton">Previous</button>
<button id="nextButton">Next</button>
<div id="output"></div>
```

JavaScript:
```javascript
let currentPage = 1;

function fetchData(page) {
  fetch(`https://jsonplaceholder.typicode.com/posts?_page=${page}`)
    .then(response => response.json())
    .then(data => {
      document.getElementById('output').textContent = JSON.stringify(data, null, 2);
    })
    .catch(error => {
      console.error('Error:', error);
      document.getElementById('output').textContent = 'An error occurred.';
    });
}

document.getElementById('prevButton').addEventListener('click', () => {
  if (currentPage > 1) {
    currentPage--;
    fetchData(currentPage);
  }
});

document.getElementById('nextButton').addEventListener('click', () => {
  currentPage++;
  fetchData(currentPage);
});
```

**Exercise 10: Data Post Processing**

```javascript
fetch('https://jsonplaceholder.typicode.com/posts')
  .then(response => response.json())
  .then(posts => {
    // Filter posts with userId 1
    const filteredPosts = posts.filter(post => post.userId === 1);
    
    // Sort posts by title
    filteredPosts.sort((a, b) => a.title.localeCompare(b.title));

    console.log('Filtered and Sorted Posts:', filteredPosts);
  })
  .catch(error => console.error('Error:', error));
```

