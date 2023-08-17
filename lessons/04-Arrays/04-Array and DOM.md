Exercise 1: Dynamic List
Create a dynamic list where users can add items through an input field, and those items are displayed as a list of elements.
```html
<!DOCTYPE html>
<html>
<head>
  <title>Dynamic List</title>
</head>
<body>
  <input type="text" id="itemInput" placeholder="Enter an item">
  <button id="addItemButton">Add Item</button>
  <ul id="itemList"></ul>

  <script>
    const addItemButton = document.getElementById('addItemButton');
    const itemInput = document.getElementById('itemInput');
    const itemList = document.getElementById('itemList');

    addItemButton.addEventListener('click', () => {
      const newItem = document.createElement('li');
      newItem.textContent = itemInput.value;
      itemList.appendChild(newItem);
      itemInput.value = '';
    });
  </script>
</body>
</html>
```

Exercise 2: Todo List
Create a todo list where users can add and remove tasks using an array and the DOM.
```html
<!DOCTYPE html>
<html>
<head>
  <title>Todo List</title>
</head>
<body>
  <input type="text" id="taskInput" placeholder="Enter a task">
  <button id="addTaskButton">Add Task</button>
  <ul id="taskList"></ul>

  <script>
    const addTaskButton = document.getElementById('addTaskButton');
    const taskInput = document.getElementById('taskInput');
    const taskList = document.getElementById('taskList');
    const tasks = [];

    addTaskButton.addEventListener('click', () => {
      if (taskInput.value !== '') {
        tasks.push(taskInput.value);
        updateTaskList();
        taskInput.value = '';
      }
    });

    function updateTaskList() {
      taskList.innerHTML = '';
      tasks.forEach(task => {
        const li = document.createElement('li');
        li.textContent = task;
        li.addEventListener('click', () => {
          const index = tasks.indexOf(task);
          if (index !== -1) {
            tasks.splice(index, 1);
            updateTaskList();
          }
        });
        taskList.appendChild(li);
      });
    }
  </script>
</body>
</html>
```

Exercise 3: Shopping Cart
Implement a simple shopping cart where users can add and remove items, and the cart total is updated accordingly.
```html
<!DOCTYPE html>
<html>
<head>
  <title>Shopping Cart</title>
</head>
<body>
  <ul id="itemList">
    <li>Item 1 <button class="remove">Remove</button></li>
    <li>Item 2 <button class="remove">Remove</button></li>
    <li>Item 3 <button class="remove">Remove</button></li>
  </ul>
  <p>Total: <span id="total">0</span></p>

  <script>
    const itemList = document.getElementById('itemList');
    const totalSpan = document.getElementById('total');
    const removeButtons = document.querySelectorAll('.remove');
    const prices = [10, 20, 15];
    let total = 0;

    removeButtons.forEach((button, index) => {
      button.addEventListener('click', () => {
        total -= prices[index];
        totalSpan.textContent = total;
        itemList.removeChild(button.parentNode);
      });
    });
  </script>
</body>
</html>
```

Exercise 4: Color Palette
Create a color palette where users can select colors, and the selected colors are displayed in a preview box.
```html
<!DOCTYPE html>
<html>
<head>
  <title>Color Palette</title>
</head>
<body>
  <div id="colorPalette">
    <input type="color" id="colorInput">
    <button id="addColorButton">Add Color</button>
  </div>
  <div id="colorPreview"></div>

  <script>
    const colorInput = document.getElementById('colorInput');
    const addColorButton = document.getElementById('addColorButton');
    const colorPreview = document.getElementById('colorPreview');
    const colors = [];

    addColorButton.addEventListener('click', () => {
      colors.push(colorInput.value);
      updateColorPreview();
      colorInput.value = '#000000'; // Reset input to default color
    });

    function updateColorPreview() {
      colorPreview.innerHTML = '';
      colors.forEach(color => {
        const colorBox = document.createElement('div');
        colorBox.style.backgroundColor = color;
        colorPreview.appendChild(colorBox);
      });
    }
  </script>
</body>
</html>
```

Exercise 5: Image Gallery
Create an image gallery where users can click on thumbnails to display a larger image.
```html
<!DOCTYPE html>
<html>
<head>
  <title>Image Gallery</title>
</head>
<body>
  <div id="imageGallery">
    <img src="image1.jpg" alt="Image 1" class="thumbnail">
    <img src="image2.jpg" alt="Image 2" class="thumbnail">
    <img src="image3.jpg" alt="Image 3" class="thumbnail">
  </div>
  <div id="largerImage"></div>

  <script>
    const thumbnailImages = document.querySelectorAll('.thumbnail');
    const largerImage = document.getElementById('largerImage');

    thumbnailImages.forEach(thumbnail => {
      thumbnail.addEventListener('click', () => {
        largerImage.innerHTML = '';
        const largerImg = document.createElement('img');
        largerImg.src = thumbnail.src;
        largerImg.alt = thumbnail.alt;
        largerImage.appendChild(largerImg);
      });
    });
  </script>
</body>
</html>
```

Exercise 6: Dynamic Table
Create a dynamic table where users can add and remove rows using an array and the DOM.
```html
<!DOCTYPE html>
<html>
<head>
  <title>Dynamic Table</title>
</head>
<body>
  <button id="addRowButton">Add Row</button>
  <table id="dataTable">
    <tr>
      <th>Name</th>
      <th>Age</th>
      <th>Action</th>
    </tr>
  </table>

  <script>
    const addRowButton = document.getElementById('addRowButton');
    const dataTable = document.getElementById('dataTable');
    const data = [];

    addRowButton.addEventListener('click', () => {
      const newRow = document.createElement('tr');
      const nameCell = document.createElement('td');
      const ageCell = document.createElement('td');
      const actionCell = document.createElement('td');
      const removeButton = document.createElement('button');

      nameCell.textContent = prompt('Enter name:');
      ageCell.textContent = prompt('Enter age:');
      removeButton.textContent = 'Remove';
      removeButton.addEventListener('click', () => {
        const rowIndex = data.indexOf(newRow);
        if (rowIndex !== -1) {
          data.splice(rowIndex, 1);
          dataTable.removeChild(newRow);
        }
      });

      actionCell.appendChild(removeButton);
      newRow.appendChild(nameCell);
      newRow.appendChild(ageCell);
      newRow.appendChild(actionCell);
      dataTable.appendChild(newRow);
      data.push(newRow);
    });
  </script>
</body>
</html>
```
