---
title: "Functions and DOM Exercises"
---

**Exercise 1: Change Text Content**
Write a function that changes the text content of an HTML element with a given ID.

```html
<!DOCTYPE html>
<html>
<head>
    <title>Change Text Content</title>
</head>
<body>
    <p id="myParagraph">This is some initial text.</p>
    <button onclick="changeText()">Change Text</button>
    <script>
        function changeText() {
            const paragraph = document.getElementById("myParagraph");
            paragraph.textContent = "Text has been changed!";
        }
    </script>
</body>
</html>
```

**Exercise 2: Toggle Visibility**
Write a function that toggles the visibility of an HTML element when a button is clicked.

```html
<!DOCTYPE html>
<html>
<head>
    <title>Toggle Visibility</title>
</head>
<body>
    <div id="myDiv" style="display: block;">This is a visible div.</div>
    <button onclick="toggleVisibility()">Toggle Visibility</button>
    <script>
        function toggleVisibility() {
            const div = document.getElementById("myDiv");
            div.style.display = div.style.display === "none" ? "block" : "none";
        }
    </script>
</body>
</html>
```

**Exercise 3: Create List Items**
Write a function that adds new list items to an unordered list when a button is clicked.

```html
<!DOCTYPE html>
<html>
<head>
    <title>Create List Items</title>
</head>
<body>
    <ul id="myList"></ul>
    <button onclick="addListItem()">Add List Item</button>
    <script>
        function addListItem() {
            const myList = document.getElementById("myList");
            const newItem = document.createElement("li");
            newItem.textContent = "New List Item";
            myList.appendChild(newItem);
        }
    </script>
</body>
</html>
```

**Exercise 4: Change Style**
Write a function that changes the style of an HTML element when a button is clicked.

```html
<!DOCTYPE html>
<html>
<head>
    <title>Change Style</title>
    <style>
        .highlighted {
            background-color: yellow;
        }
    </style>
</head>
<body>
    <p id="myParagraph">This is a paragraph.</p>
    <button onclick="changeStyle()">Highlight</button>
    <script>
        function changeStyle() {
            const paragraph = document.getElementById("myParagraph");
            paragraph.classList.toggle("highlighted");
        }
    </script>
</body>
</html>
```

**Exercise 5: Calculate and Display**
Write a function that calculates the sum of two numbers entered by the user and displays the result.

```html
<!DOCTYPE html>
<html>
<head>
    <title>Calculate and Display</title>
</head>
<body>
    <input type="number" id="num1" placeholder="Enter number 1">
    <input type="number" id="num2" placeholder="Enter number 2">
    <button onclick="calculateSum()">Calculate Sum</button>
    <p id="result"></p>
    <script>
        function calculateSum() {
            const num1 = parseFloat(document.getElementById("num1").value);
            const num2 = parseFloat(document.getElementById("num2").value);
            const sum = num1 + num2;
            document.getElementById("result").textContent = `Sum: ${sum}`;
        }
    </script>
</body>
</html>
```

