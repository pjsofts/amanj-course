---
title: "DOM Exercises Answers"
description: "DOM Exercises Answers"
---

**Exercise 1: Changing Text Content**

HTML:
```html
<p id="myText">This is some initial text content.</p>
<button id="changeTextButton">Change Text</button>
```

JavaScript:
```javascript
const changeTextButton = document.getElementById("changeTextButton");
const myText = document.getElementById("myText");

changeTextButton.addEventListener("click", function() {
  myText.textContent = "The text has been changed!";
});
```

**Exercise 2: Changing Styles**

HTML:
```html
<div id="myDiv">This is a div element.</div>
<button id="changeColorButton">Change Color</button>
```

JavaScript:
```javascript
const changeColorButton = document.getElementById("changeColorButton");
const myDiv = document.getElementById("myDiv");

changeColorButton.addEventListener("click", function() {
  myDiv.style.backgroundColor = "blue";
});
```

**Exercise 3: Adding Elements**

HTML:
```html
<button id="addItemButton">Add Item</button>
<ul id="myList"></ul>
```

JavaScript:
```javascript
const addItemButton = document.getElementById("addItemButton");
const myList = document.getElementById("myList");

addItemButton.addEventListener("click", function() {
  const listItem = document.createElement("li");
  listItem.textContent = "New item";
  myList.appendChild(listItem);
});
```

**Exercise 4: Removing Elements**

HTML:
```html
<ul id="myList">
  <li>Item 1</li>
  <li>Item 2</li>
  <li>Item 3</li>
</ul>
<button id="removeItemButton">Remove Item</button>
```

JavaScript:
```javascript
const removeItemButton = document.getElementById("removeItemButton");
const myList = document.getElementById("myList");

removeItemButton.addEventListener("click", function() {
  if (myList.children.length > 0) {
    myList.removeChild(myList.lastElementChild);
  }
});
```

**Exercise 5: Creating a To-Do List**

HTML:
```html
<input type="text" id="taskInput" placeholder="Enter a task">
<button id="addTaskButton">Add Task</button>
<ul id="taskList"></ul>
```

JavaScript:
```javascript
const taskInput = document.getElementById("taskInput");
const addTaskButton = document.getElementById("addTaskButton");
const taskList = document.getElementById("taskList");

addTaskButton.addEventListener("click", function() {
  const taskText = taskInput.value;
  if (taskText.trim() !== "") {
    const listItem = document.createElement("li");
    listItem.textContent = taskText;
    taskList.appendChild(listItem);
    taskInput.value = "";
  }
});
```
