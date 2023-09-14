---
title: "Answers to Programming Exercises Using Objects "
---

**Exercise 1: Word Frequency Counter:**
```javascript
function wordFrequency(sentence) {
  const words = sentence.toLowerCase().split(/\s+/);
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

const sentence = "This is a simple sentence. Is it simple?";
console.log(wordFrequency(sentence));
```

**Exercise 2: Shopping Cart:**
```javascript
class ShoppingCart {
  constructor() {
    this.items = [];
  }

  addItem(item) {
    this.items.push(item);
  }

  removeItem(item) {
    const index = this.items.indexOf(item);
    if (index !== -1) {
      this.items.splice(index, 1);
    }
  }

  getTotalPrice() {
    return this.items.reduce((total, item) => total + item.price, 0);
  }
}

class Item {
  constructor(name, price) {
    this.name = name;
    this.price = price;
  }
}

const cart = new ShoppingCart();
const item1 = new Item("Shirt", 25);
const item2 = new Item("Jeans", 50);

cart.addItem(item1);
cart.addItem(item2);
console.log(cart.getTotalPrice());
```

**Exercise 3: Library Catalog:**
```javascript
class Book {
  constructor(title, author) {
    this.title = title;
    this.author = author;
    this.borrowed = false;
  }

  borrow() {
    if (!this.borrowed) {
      this.borrowed = true;
      return true;
    }
    return false;
  }

  returnBook() {
    this.borrowed = false;
  }
}

class LibraryCatalog {
  constructor() {
    this.books = [];
  }

  addBook(book) {
    this.books.push(book);
  }

  searchByTitle(title) {
    return this.books.filter(book => book.title.toLowerCase().includes(title.toLowerCase()));
  }

  searchByAuthor(author) {
    return this.books.filter(book => book.author.toLowerCase().includes(author.toLowerCase()));
  }
}

const library = new LibraryCatalog();
const book1 = new Book("The Great Gatsby", "F. Scott Fitzgerald");
const book2 = new Book("To Kill a Mockingbird", "Harper Lee");

library.addBook(book1);
library.addBook(book2);

console.log(library.searchByTitle("great"));
console.log(library.searchByAuthor("Harper Lee"));
```


**Exercise 4: Contact List:**
```javascript
class Contact {
  constructor(name, email, phone) {
    this.name = name;
    this.email = email;
    this.phone = phone;
  }
}

class ContactList {
  constructor() {
    this.contacts = [];
  }

  addContact(contact) {
    this.contacts.push(contact);
  }

  removeContact(contact) {
    const index = this.contacts.indexOf(contact);
    if (index !== -1) {
      this.contacts.splice(index, 1);
    }
  }

  searchByName(name) {
    return this.contacts.filter(contact => contact.name.toLowerCase().includes(name.toLowerCase()));
  }
}

const contactList = new ContactList();
const contact1 = new Contact("Alice Smith", "alice@example.com", "123-456-7890");
const contact2 = new Contact("Bob Johnson", "bob@example.com", "987-654-3210");

contactList.addContact(contact1);
contactList.addContact(contact2);

console.log(contactList.searchByName("Alice"));
```

**Exercise 5: Quiz App:**
```javascript
class Question {
  constructor(text, options, correctOption) {
    this.text = text;
    this.options = options;
    this.correctOption = correctOption;
  }
}

class Quiz {
  constructor() {
    this.questions = [];
    this.score = 0;
  }

  addQuestion(question) {
    this.questions.push(question);
  }

  submitAnswer(questionIndex, answerIndex) {
    if (this.questions[questionIndex].correctOption === answerIndex) {
      this.score++;
    }
  }
}

const question1 = new Question("What is the capital of France?", ["Paris", "Berlin", "London"], 0);
const question2 = new Question("Which planet is known as the Red Planet?", ["Mars", "Venus", "Earth"], 0);

const quiz = new Quiz();
quiz.addQuestion(question1);
quiz.addQuestion(question2);

quiz.submitAnswer(0, 0);
quiz.submitAnswer(1, 1);

console.log(`Your score: ${quiz.score}`);
```

**Exercise 6: Task Tracker:**
```javascript
class Task {
  constructor(title, description, dueDate) {
    this.title = title;
    this.description = description;
    this.dueDate = dueDate;
    this.completed = false;
  }

  markCompleted() {
    this.completed = true;
  }
}

class TaskTracker {
  constructor() {
    this.tasks = [];
  }

  addTask(task) {
    this.tasks.push(task);
  }

  markTaskCompleted(task) {
    task.markCompleted();
  }

  getIncompleteTasks() {
    return this.tasks.filter(task => !task.completed);
  }
}

const task1 = new Task("Complete project", "Finish coding the project", "2023-08-31");
const task2 = new Task("Buy groceries", "Get milk, eggs, and bread", "2023-08-20");

const taskTracker = new TaskTracker();
taskTracker.addTask(task1);
taskTracker.addTask(task2);

taskTracker.markTaskCompleted(task1);

console.log(taskTracker.getIncompleteTasks());
```

**Exercise 7: Calendar Scheduler:**

```html
<!DOCTYPE html>
<html>
<head>
    <title>Calendar Scheduler</title>
    <style>
        /* Add some CSS styling for the calendar */
        #calendar {
            width: 400px;
            margin: 0 auto;
            border-collapse: collapse;
        }

        #calendar th, #calendar td {
            border: 1px solid #ccc;
            padding: 5px;
            text-align: center;
        }
    </style>
</head>
<body>
    <h1>Calendar Scheduler</h1>
    <div id="event-form">
        <label for="event-date">Event Date:</label>
        <input type="date" id="event-date">
        <label for="event-description">Event Description:</label>
        <input type="text" id="event-description">
        <button onclick="addEvent()">Add Event</button>
    </div>
    <table id="calendar">
        <thead>
            <tr>
                <th>Sunday</th>
                <th>Monday</th>
                <th>Tuesday</th>
                <th>Wednesday</th>
                <th>Thursday</th>
                <th>Friday</th>
                <th>Saturday</th>
            </tr>
        </thead>
        <tbody>
        </tbody>
    </table>

    <script>
        // Object to store events
        const calendar = {};

        // Function to add an event to the calendar
        function addEvent() {
            const dateInput = document.getElementById('event-date');
            const descriptionInput = document.getElementById('event-description');
            const date = dateInput.value;
            const description = descriptionInput.value;

            if (!date || !description) {
                alert('Please enter both date and description.');
                return;
            }

            if (!calendar[date]) {
                calendar[date] = [];
            }

            calendar[date].push(description);
            dateInput.value = '';
            descriptionInput.value = '';
            updateCalendar();
        }

        // Function to update the calendar display
        function updateCalendar() {
            const tableBody = document.querySelector('#calendar tbody');
            tableBody.innerHTML = '';

            for (const date in calendar) {
                const eventList = calendar[date];
                const row = tableBody.insertRow();
                const cell = row.insertCell();
                cell.colSpan = 7;
                cell.textContent = date;

                for (const event of eventList) {
                    const row = tableBody.insertRow();
                    const cell = row.insertCell();
                    cell.textContent = event;
                }
            }
        }

        // Initial calendar update
        updateCalendar();
    </script>
</body>
</html>
```



**Exercise 8: Social Media Profile:**

```html
<!DOCTYPE html>
<html>
<head>
    <title>Social Media Profile</title>
</head>
<body>
    <h1>Social Media Profile</h1>
    
    <div id="profile-form">
        <label for="username">Username:</label>
        <input type="text" id="username">
        <button onclick="createProfile()">Create Profile</button>
    </div>

    <div id="user-profile">
        <h2>User Profile</h2>
        <p><strong>Username:</strong> <span id="profile-username"></span></p>
        <p><strong>Friends:</strong> <span id="profile-friends"></span></p>
    </div>

    <div id="friend-form">
        <label for="friend-username">Friend's Username:</label>
        <input type="text" id="friend-username">
        <button onclick="addFriend()">Add Friend</button>
    </div>

    <script>
        // Object to store user profiles
        const profiles = {};

        // Function to create a user profile
        function createProfile() {
            const usernameInput = document.getElementById('username');
            const username = usernameInput.value;

            if (!username) {
                alert('Please enter a username.');
                return;
            }

            if (profiles[username]) {
                alert('Profile already exists for this username.');
                return;
            }

            profiles[username] = {
                username: username,
                friends: []
            };

            // Display the user profile
            const userProfile = document.getElementById('user-profile');
            const profileUsername = document.getElementById('profile-username');
            const profileFriends = document.getElementById('profile-friends');

            profileUsername.textContent = username;
            profileFriends.textContent = 'No friends yet';

            usernameInput.value = '';
        }

        // Function to add a friend to the user's profile
        function addFriend() {
            const usernameInput = document.getElementById('username');
            const friendUsernameInput = document.getElementById('friend-username');

            const username = usernameInput.value;
            const friendUsername = friendUsernameInput.value;

            if (!profiles[username] || !profiles[friendUsername]) {
                alert('User profile or friend profile does not exist.');
                return;
            }

            profiles[username].friends.push(friendUsername);

            // Update the friend list in the user's profile
            const profileFriends = document.getElementById('profile-friends');
            profileFriends.textContent = profiles[username].friends.join(', ');

            friendUsernameInput.value = '';
        }
    </script>
</body>
</html>
```

**Exercise 9: Student Management System:**

```html
<!DOCTYPE html>
<html>
<head>
    <title>Student Management System</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f0f0f0;
        }

        h1 {
            background-color: #333;
            color: #fff;
            padding: 20px;
            text-align: center;
        }

        #container {
            width: 80%;
            margin: 0 auto;
            background-color: #fff;
            padding: 20px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
        }

        table {
            width: 100%;
            border-collapse: collapse;
            margin-top: 20px;
        }

        table, th, td {
            border: 1px solid #ccc;
        }

        th, td {
            padding: 10px;
            text-align: left;
        }

        th {
            background-color: #333;
            color: #fff;
        }

        tr:nth-child(even) {
            background-color: #f2f2f2;
        }

        button {
            padding: 5px 10px;
            background-color: #333;
            color: #fff;
            border: none;
            cursor: pointer;
        }

        button:hover {
            background-color: #555;
        }
    </style>
</head>
<body>
    <h1>Student Management System</h1>
    <div id="container">
        <h2>Add Student</h2>
        <label for="student-name">Name:</label>
        <input type="text" id="student-name">
        <label for="student-grade">Grade:</label>
        <input type="number" id="student-grade">
        <button onclick="addStudent()">Add Student</button>

        <h2>Student List</h2>
        <table>
            <thead>
                <tr>
                    <th>Name</th>
                    <th>Grade</th>
                    <th>Attendance</th>
                    <th>Action</th>
                </tr>
            </thead>
            <tbody id="student-list">
            </tbody>
        </table>
    </div>

    <script>
        // Object to store student information
        const students = [];

        // Function to add a student
        function addStudent() {
            const studentNameInput = document.getElementById('student-name');
            const studentGradeInput = document.getElementById('student-grade');
            const studentName = studentNameInput.value;
            const studentGrade = studentGradeInput.value;

            if (!studentName || !studentGrade) {
                alert('Please enter both name and grade.');
                return;
            }

            students.push({
                name: studentName,
                grade: parseFloat(studentGrade),
                attendance: 0
            });

            studentNameInput.value = '';
            studentGradeInput.value = '';

            updateStudentList();
        }

        // Function to update the student list
        function updateStudentList() {
            const studentList = document.getElementById('student-list');
            studentList.innerHTML = '';

            for (let i = 0; i < students.length; i++) {
                const student = students[i];
                const row = studentList.insertRow();
                const nameCell = row.insertCell(0);
                const gradeCell = row.insertCell(1);
                const attendanceCell = row.insertCell(2);
                const actionCell = row.insertCell(3);

                nameCell.textContent = student.name;
                gradeCell.textContent = student.grade.toFixed(2);
                attendanceCell.textContent = student.attendance;
                actionCell.innerHTML = `<button onclick="markAttendance(${i})">Mark Attendance</button>`;
            }
        }

        // Function to mark attendance for a student
        function markAttendance(index) {
            students[index].attendance++;
            updateStudentList();
        }
    </script>
</body>
</html>
```





**Exercise 10: Recipe Book:**

```html
<!DOCTYPE html>
<html>
<head>
    <title>Recipe Book</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f0f0f0;
        }

        h1 {
            background-color: #333;
            color: #fff;
            padding: 20px;
            text-align: center;
        }

        #container {
            width: 80%;
            margin: 0 auto;
            background-color: #fff;
            padding: 20px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
        }

        #recipe-form {
            display: flex;
            flex-direction: column;
            margin-top: 20px;
        }

        label {
            font-weight: bold;
            margin-bottom: 5px;
        }

        input[type="text"], textarea {
            padding: 10px;
            margin-bottom: 10px;
            border: 1px solid #ccc;
            border-radius: 4px;
        }

        #recipe-list {
            margin-top: 20px;
        }

        .recipe {
            border: 1px solid #ccc;
            border-radius: 4px;
            padding: 10px;
            margin-bottom: 10px;
            background-color: #fff;
        }

        .recipe h3 {
            margin: 0;
        }

        .recipe p {
            margin: 5px 0;
        }
    </style>
</head>
<body>
    <h1>Recipe Book</h1>
    <div id="container">
        <h2>Add Recipe</h2>
        <div id="recipe-form">
            <label for="recipe-name">Recipe Name:</label>
            <input type="text" id="recipe-name">
            <label for="recipe-ingredients">Ingredients:</label>
            <textarea id="recipe-ingredients" rows="4"></textarea>
            <label for="recipe-instructions">Instructions:</label>
            <textarea id="recipe-instructions" rows="4"></textarea>
            <button onclick="addRecipe()">Add Recipe</button>
        </div>

        <h2>Recipe List</h2>
        <div id="recipe-list">
        </div>
    </div>

    <script>
        // Array to store recipes
        const recipes = [];

        // Function to add a recipe
        function addRecipe() {
            const recipeNameInput = document.getElementById('recipe-name');
            const recipeIngredientsInput = document.getElementById('recipe-ingredients');
            const recipeInstructionsInput = document.getElementById('recipe-instructions');

            const name = recipeNameInput.value;
            const ingredients = recipeIngredientsInput.value;
            const instructions = recipeInstructionsInput.value;

            if (!name || !ingredients || !instructions) {
                alert('Please enter recipe name, ingredients, and instructions.');
                return;
            }

            const recipe = {
                name: name,
                ingredients: ingredients,
                instructions: instructions
            };

            recipes.push(recipe);

            recipeNameInput.value = '';
            recipeIngredientsInput.value = '';
            recipeInstructionsInput.value = '';

            updateRecipeList();
        }

        // Function to update the recipe list
        function updateRecipeList() {
            const recipeList = document.getElementById('recipe-list');
            recipeList.innerHTML = '';

            for (let i = 0; i < recipes.length; i++) {
                const recipe = recipes[i];
                const recipeElement = document.createElement('div');
                recipeElement.classList.add('recipe');

                recipeElement.innerHTML = `
                    <h3>${recipe.name}</h3>
                    <p><strong>Ingredients:</strong></p>
                    <p>${recipe.ingredients}</p>
                    <p><strong>Instructions:</strong></p>
                    <p>${recipe.instructions}</p>
                `;

                recipeList.appendChild(recipeElement);
            }
        }
    </script>
</body>
</html>
```



**Exercise 11: Game Character Inventory:**

```html
<!DOCTYPE html>
<html>
<head>
    <title>Game Character Inventory</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f0f0f0;
        }

        h1 {
            background-color: #333;
            color: #fff;
            padding: 20px;
            text-align: center;
        }

        #container {
            width: 80%;
            margin: 0 auto;
            background-color: #fff;
            padding: 20px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
        }

        h2 {
            margin-top: 0;
        }

        .inventory-item {
            display: flex;
            justify-content: space-between;
            border: 1px solid #ccc;
            border-radius: 4px;
            padding: 10px;
            margin-bottom: 10px;
            background-color: #fff;
        }

        .inventory-item h3 {
            margin: 0;
        }

        .inventory-item .item-info {
            flex-grow: 1;
            margin-right: 10px;
        }

        .inventory-item .item-actions button {
            padding: 5px 10px;
            background-color: #333;
            color: #fff;
            border: none;
            cursor: pointer;
        }

        .inventory-item .item-actions button:hover {
            background-color: #555;
        }
    </style>
</head>
<body>
    <h1>Game Character Inventory</h1>
    <div id="container">
        <h2>Inventory</h2>
        <div id="inventory">
        </div>

        <h2>Add Item</h2>
        <div id="add-item-form">
            <label for="item-name">Item Name:</label>
            <input type="text" id="item-name">
            <label for="item-description">Item Description:</label>
            <textarea id="item-description" rows="4"></textarea>
            <button onclick="addItem()">Add Item</button>
        </div>
    </div>

    <script>
        // Array to store inventory items
        const inventory = [];

        // Function to add an item to the inventory
        function addItem() {
            const itemNameInput = document.getElementById('item-name');
            const itemDescriptionInput = document.getElementById('item-description');

            const name = itemNameInput.value;
            const description = itemDescriptionInput.value;

            if (!name || !description) {
                alert('Please enter both item name and description.');
                return;
            }

            const item = {
                name: name,
                description: description
            };

            inventory.push(item);

            itemNameInput.value = '';
            itemDescriptionInput.value = '';

            updateInventory();
        }

        // Function to remove an item from the inventory
        function removeItem(index) {
            inventory.splice(index, 1);
            updateInventory();
        }

        // Function to update the inventory display
        function updateInventory() {
            const inventoryContainer = document.getElementById('inventory');
            inventoryContainer.innerHTML = '';

            for (let i = 0; i < inventory.length; i++) {
                const item = inventory[i];
                const itemElement = document.createElement('div');
                itemElement.classList.add('inventory-item');

                itemElement.innerHTML = `
                    <div class="item-info">
                        <h3>${item.name}</h3>
                        <p>${item.description}</p>
                    </div>
                    <div class="item-actions">
                        <button onclick="removeItem(${i})">Remove</button>
                    </div>
                `;

                inventoryContainer.appendChild(itemElement);
            }
        }
    </script>
</body>
</html>
```



**Exercise 12: Weather Data Logger:**

```html
<!DOCTYPE html>
<html>
<head>
    <title>Weather Data Logger</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f0f0f0;
        }

        h1 {
            background-color: #4CAF50;
            color: #fff;
            padding: 20px;
            text-align: center;
            margin: 0;
        }

        #container {
            width: 80%;
            margin: 20px auto;
            background-color: #fff;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
        }

        h2 {
            background-color: #4CAF50;
            color: #fff;
            padding: 10px;
            margin: 0;
        }

        #location-form {
            padding: 20px;
            display: flex;
            flex-direction: column;
        }

        label {
            font-weight: bold;
            margin-bottom: 5px;
        }

        input[type="text"] {
            padding: 10px;
            margin-bottom: 10px;
            border: 1px solid #ccc;
            border-radius: 4px;
        }

        #weather-list {
            padding: 20px;
        }

        .weather-card {
            background-color: #4CAF50;
            color: #fff;
            padding: 10px;
            margin-bottom: 10px;
            border-radius: 4px;
        }

        .weather-card h3 {
            margin: 0;
        }

        .weather-card p {
            margin: 5px 0;
        }

        .error-card {
            background-color: #FF5733;
            color: #fff;
            padding: 10px;
            margin-bottom: 10px;
            border-radius: 4px;
        }
    </style>
</head>
<body>
    <h1>Weather Data Logger</h1>
    <div id="container">
        <h2>Log Weather Data</h2>
        <div id="location-form">
            <label for="location">Location:</label>
            <input type="text" id="location">
            <button onclick="logWeather()">Log Weather</button>
        </div>

        <h2>Weather Log</h2>
        <div id="weather-list">
        </div>
    </div>

    <script>
        // Object to store weather log
        const weatherLog = [];

        // Function to log weather data
        function logWeather() {
            const locationInput = document.getElementById('location');
            const location = locationInput.value;

            if (!location) {
                displayError('Please enter a location.');
                return;
            }

            // Simulate fetching weather data (replace with real API call)
            const weatherData = {
                temperature: Math.floor(Math.random() * 30) + 15, // Random temperature between 15°C and 44°C
                humidity: Math.floor(Math.random() * 60) + 40, // Random humidity between 40% and 99%
                windSpeed: Math.floor(Math.random() * 20) + 5, // Random wind speed between 5 km/h and 24 km/h
            };

            weatherLog.push({
                location: location,
                weatherData: weatherData,
                timestamp: new Date().toLocaleString()
            });

            locationInput.value = '';

            // Display the latest weather log
            updateWeatherLog();
        }

        // Function to display an error message
        function displayError(message) {
            const errorCard = document.createElement('div');
            errorCard.classList.add('error-card');
            errorCard.textContent = message;
            document.getElementById('weather-list').appendChild(errorCard);
        }

        // Function to update the weather log display
        function updateWeatherLog() {
            const weatherList = document.getElementById('weather-list');
            weatherList.innerHTML = '';

            for (let i = 0; i < weatherLog.length; i++) {
                const log = weatherLog[i];
                const weatherCard = document.createElement('div');
                weatherCard.classList.add('weather-card');

                weatherCard.innerHTML = `
                    <h3>${log.location}</h3>
                    <p>Temperature: ${log.weatherData.temperature}°C</p>
                    <p>Humidity: ${log.weatherData.humidity}%</p>
                    <p>Wind Speed: ${log.weatherData.windSpeed} km/h</p>
                    <p>Timestamp: ${log.timestamp}</p>
                `;

                weatherList.appendChild(weatherCard);
            }
        }
    </script>
</body>
</html>
```


**Exercise 13: Online Store Checkout:**

```html
<!DOCTYPE html>
<html>
<head>
    <title>Online Store Checkout</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            background: linear-gradient(135deg, #0A84FF, #2A2A72);
        }

        h1 {
            background-color: #fff;
            color: #2A2A72;
            padding: 20px;
            text-align: center;
            margin: 0;
        }

        #container {
            width: 80%;
            margin: 20px auto;
            background-color: #fff;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.2);
            border-radius: 10px;
            overflow: hidden;
        }

        #cart {
            padding: 20px;
        }

        #cart h2 {
            margin: 0;
            padding: 10px;
            background-color: #2A2A72;
            color: #fff;
        }

        #cart-items {
            padding: 20px;
        }

        .cart-item {
            display: flex;
            justify-content: space-between;
            padding: 10px 20px;
            border-bottom: 1px solid #ccc;
        }

        .cart-item:last-child {
            border-bottom: none;
        }

        .cart-item p {
            margin: 0;
        }

        .cart-item .item-name {
            flex-grow: 1;
            margin-right: 10px;
            font-weight: bold;
        }

        .cart-item .item-price {
            font-weight: bold;
            color: #2A2A72;
        }

        #checkout {
            padding: 20px;
            background-color: #2A2A72;
            color: #fff;
            text-align: center;
        }

        #checkout button {
            padding: 10px 20px;
            background-color: #0A84FF;
            color: #fff;
            border: none;
            cursor: pointer;
            border-radius: 4px;
        }

        #checkout button:hover {
            background-color: #0091E0;
        }
    </style>
</head>
<body>
    <h1>Online Store Checkout</h1>
    <div id="container">
        <div id="cart">
            <h2>Shopping Cart</h2>
            <div id="cart-items">
            </div>
        </div>

        <div id="checkout">
            <h2>Total:</h2>
            <p id="total-price">$0.00</p>
            <button onclick="checkout()">Checkout</button>
        </div>
    </div>

    <script>
        // Object to store cart items
        const cart = [];

        // Function to add an item to the cart
        function addItem(name, price) {
            cart.push({ name, price });
            updateCart();
        }

        // Function to update the cart display
        function updateCart() {
            const cartItems = document.getElementById('cart-items');
            cartItems.innerHTML = '';
            let totalPrice = 0;

            cart.forEach((item) => {
                const itemElement = document.createElement('div');
                itemElement.classList.add('cart-item');

                itemElement.innerHTML = `
                    <p class="item-name">${item.name}</p>
                    <p class="item-price">$${item.price.toFixed(2)}</p>
                `;

                cartItems.appendChild(itemElement);
                totalPrice += item.price;
            });

            const totalPriceElement = document.getElementById('total-price');
            totalPriceElement.textContent = `$${totalPrice.toFixed(2)}`;
        }

        // Function to handle checkout
        function checkout() {
            if (cart.length === 0) {
                alert('Your cart is empty. Add items to your cart before checking out.');
                return;
            }

            alert('Checkout Successful! Thank you for your purchase.');
            cart.length = 0; // Clear the cart
            updateCart();
        }

        // Example: Add some items to the cart
        addItem('Item 1', 9.99);
        addItem('Item 2', 14.99);
        addItem('Item 3', 19.99);
    </script>
</body>
</html>
```


**Exercise 14: Music Playlist Manager:**

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Music Playlist Manager</title>
    <style>
        body {
            font-family: 'Arial', sans-serif;
            margin: 0;
            padding: 0;
            background-color: #222;
            color: #fff;
        }

        h1 {
            background-color: #333;
            color: #fff;
            padding: 20px;
            text-align: center;
            margin: 0;
        }

        #container {
            width: 80%;
            margin: 20px auto;
            background-color: #444;
            border-radius: 10px;
            padding: 20px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.3);
        }

        h2 {
            color: #0A84FF;
        }

        #playlist {
            padding: 20px;
        }

        .playlist-item {
            display: flex;
            justify-content: space-between;
            align-items: center;
            background-color: #333;
            padding: 10px;
            border-radius: 5px;
            margin-bottom: 10px;
        }

        .playlist-item .item-info {
            flex-grow: 1;
            margin-right: 10px;
            overflow: hidden;
        }

        .playlist-item .item-title {
            font-size: 18px;
            font-weight: bold;
            color: #0A84FF;
        }

        .playlist-item .item-artist {
            font-size: 14px;
            color: #ccc;
        }

        .playlist-item .item-actions button {
            padding: 5px 10px;
            background-color: #0A84FF;
            color: #fff;
            border: none;
            cursor: pointer;
            border-radius: 5px;
        }

        .playlist-item .item-actions button:hover {
            background-color: #0077D6;
        }

        #add-form {
            padding: 20px;
            background-color: #333;
            border-radius: 5px;
        }

        #add-form label, #add-form input, #add-form button {
            margin-bottom: 10px;
            display: block;
        }

        #add-form label, #add-form button {
            color: #0A84FF;
        }

        #add-form input[type="text"] {
            padding: 10px;
            border: none;
            border-radius: 5px;
        }

        #add-form button {
            padding: 10px 20px;
            background-color: #0A84FF;
            border: none;
            border-radius: 5px;
            cursor: pointer;
        }

        #add-form button:hover {
            background-color: #0077D6;
        }
    </style>
</head>
<body>
    <h1>Music Playlist Manager</h1>
    <div id="container">
        <h2>My Playlist</h2>
        <div id="playlist">
        </div>

        <h2>Add a Song</h2>
        <div id="add-form">
            <label for="song-title">Title:</label>
            <input type="text" id="song-title" placeholder="Song Title">
            <label for="song-artist">Artist:</label>
            <input type="text" id="song-artist" placeholder="Artist">
            <button onclick="addSong()">Add Song</button>
        </div>
    </div>

    <script>
        // Object to store playlist
        const playlist = [];

        // Function to add a song to the playlist
        function addSong() {
            const songTitleInput = document.getElementById('song-title');
            const songArtistInput = document.getElementById('song-artist');

            const title = songTitleInput.value;
            const artist = songArtistInput.value;

            if (!title || !artist) {
                alert('Please enter both song title and artist.');
                return;
            }

            playlist.push({ title, artist });
            songTitleInput.value = '';
            songArtistInput.value = '';

            updatePlaylist();
        }

        // Function to update the playlist display
        function updatePlaylist() {
            const playlistContainer = document.getElementById('playlist');
            playlistContainer.innerHTML = '';

            playlist.forEach((song, index) => {
                const songItem = document.createElement('div');
                songItem.classList.add('playlist-item');

                songItem.innerHTML = `
                    <div class="item-info">
                        <p class="item-title">${song.title}</p>
                        <p class="item-artist">${song.artist}</p>
                    </div>
                    <div class="item-actions">
                        <button onclick="removeSong(${index})">Remove</button>
                    </div>
                `;

                playlistContainer.appendChild(songItem);
            });
        }

        // Function to remove a song from the playlist
        function removeSong(index) {
            playlist.splice(index, 1);
            updatePlaylist();
        }

        // Example: Add some initial songs to the playlist
        playlist.push({ title: 'Song 1', artist: 'Artist 1' });
        playlist.push({ title: 'Song 2', artist: 'Artist 2' });

        // Initial update of the playlist
        updatePlaylist();
    </script>
</body>
</html>
```



**Exercise 15: Language Flashcards:**

```html
<!DOCTYPE html>
<html>
<head>
    <title>Language Flashcards</title>
    <style>
        body {
            font-family: 'Arial', sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f5f5f5;
        }

        h1 {
            background-color: #0A84FF;
            color: #fff;
            padding: 20px;
            text-align: center;
            margin: 0;
        }

        #container {
            width: 80%;
            margin: 20px auto;
            background-color: #fff;
            border-radius: 10px;
            padding: 20px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.2);
        }

        h2 {
            color: #0A84FF;
        }

        #flashcard-container {
            padding: 20px;
            text-align: center;
            position: relative;
            width: 300px;
            height: 150px;
            margin: 0 auto;
            perspective: 1000px;
        }

        .flashcard {
            width: 100%;
            height: 100%;
            background-color: #fff;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
            border-radius: 10px;
            position: absolute;
            transition: transform 0.5s;
            transform-style: preserve-3d;
            cursor: pointer;
        }

        .flashcard.front {
            transform: rotateY(0deg);
            display: flex;
            justify-content: center;
            align-items: center;
        }

        .flashcard.back {
            transform: rotateY(180deg);
            display: flex;
            justify-content: center;
            align-items: center;
        }

        .flashcard p {
            font-size: 24px;
            margin: 0;
        }

        #flashcard-buttons {
            text-align: center;
            margin-top: 20px;
        }

        button {
            padding: 10px 20px;
            background-color: #0A84FF;
            color: #fff;
            border: none;
            border-radius: 5px;
            cursor: pointer;
        }

        button:hover {
            background-color: #0077D6;
        }
    </style>
</head>
<body>
    <h1>Language Flashcards</h1>
    <div id="container">
        <h2>Flashcards</h2>
        <div id="flashcard-container">
            <div class="flashcard front">
                <p id="front-card">Hello</p>
            </div>
            <div class="flashcard back">
                <p id="back-card">Bonjour</p>
            </div>
        </div>
        <div id="flashcard-buttons">
            <button onclick="showTranslation()">Show Translation</button>
            <button onclick="nextFlashcard()">Next Flashcard</button>
        </div>
    </div>

    <script>
        // Array to store flashcards
        const flashcards = [
            { front: "Hello", back: "Bonjour" },
            { front: "Goodbye", back: "Au revoir" },
            { front: "Thank you", back: "Merci" },
            { front: "Yes", back: "Oui" },
            { front: "No", back: "Non" }
        ];

        let currentFlashcardIndex = 0;
        let showingTranslation = false;

        // Function to show the translation of the current flashcard
        function showTranslation() {
            if (!showingTranslation) {
                const backCard = document.getElementById('back-card');
                backCard.textContent = flashcards[currentFlashcardIndex].back;
                showingTranslation = true;
            }
        }

        // Function to move to the next flashcard
        function nextFlashcard() {
            if (showingTranslation) {
                const backCard = document.getElementById('back-card');
                backCard.textContent = '';
                showingTranslation = false;
            }

            currentFlashcardIndex++;
            if (currentFlashcardIndex >= flashcards.length) {
                currentFlashcardIndex = 0;
            }

            const frontCard = document.getElementById('front-card');
            frontCard.textContent = flashcards[currentFlashcardIndex].front;
        }

        // Initial display
        const frontCard = document.getElementById('front-card');
        frontCard.textContent = flashcards[currentFlashcardIndex].front;
    </script>
</body>
</html>
```





**Exercise 16: Task Priority Manager:**

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Task Priority Manager</title>
    <style>
        body {
            font-family: 'Arial', sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f2f2f2;
        }

        h1 {
            background-color: #4CAF50;
            color: #fff;
            padding: 20px;
            text-align: center;
            margin: 0;
        }

        #container {
            width: 80%;
            margin: 20px auto;
            background-color: #fff;
            border-radius: 10px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.2);
            overflow: hidden;
        }

        h2 {
            background-color: #4CAF50;
            color: #fff;
            padding: 10px;
            margin: 0;
        }

        #task-list {
            padding: 20px;
            display: flex;
            flex-direction: column;
        }

        .task {
            display: flex;
            justify-content: space-between;
            align-items: center;
            background-color: #fff;
            border: 1px solid #ccc;
            border-radius: 5px;
            padding: 10px;
            margin-bottom: 10px;
            transition: transform 0.3s ease-in-out;
        }

        .task:hover {
            transform: scale(1.02);
            box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
        }

        .task p {
            margin: 0;
            font-size: 16px;
        }

        .task .priority {
            background-color: #4CAF50;
            color: #fff;
            padding: 5px 10px;
            border-radius: 4px;
        }

        #add-task-form {
            padding: 20px;
        }

        label {
            font-weight: bold;
        }

        input[type="text"] {
            width: 100%;
            padding: 10px;
            margin-bottom: 10px;
            border: 1px solid #ccc;
            border-radius: 4px;
        }

        #priority-select {
            width: 100%;
            padding: 10px;
            margin-bottom: 10px;
            border: 1px solid #ccc;
            border-radius: 4px;
        }

        #add-task-button {
            padding: 10px 20px;
            background-color: #4CAF50;
            color: #fff;
            border: none;
            border-radius: 4px;
            cursor: pointer;
        }

        #add-task-button:hover {
            background-color: #45a049;
        }
    </style>
</head>
<body>
    <h1>Task Priority Manager</h1>
    <div id="container">
        <h2>Task List</h2>
        <div id="task-list">
            <!-- Tasks will be dynamically added here -->
        </div>
        <h2>Add Task</h2>
        <div id="add-task-form">
            <label for="task-name">Task Name:</label>
            <input type="text" id="task-name" placeholder="Enter task name">
            <label for="task-priority">Priority:</label>
            <select id="priority-select">
                <option value="low">Low</option>
                <option value="medium">Medium</option>
                <option value="high">High</option>
            </select>
            <button id="add-task-button" onclick="addTask()">Add Task</button>
        </div>
    </div>

    <script>
        // Object to store tasks
        const tasks = [];

        // Function to add a task to the list
        function addTask() {
            const taskNameInput = document.getElementById('task-name');
            const prioritySelect = document.getElementById('priority-select');

            const taskName = taskNameInput.value;
            const priority = prioritySelect.value;

            if (!taskName) {
                alert('Please enter a task name.');
                return;
            }

            const task = {
                name: taskName,
                priority: priority
            };

            tasks.push(task);

            taskNameInput.value = '';
            prioritySelect.value = 'low';

            updateTaskList();
        }

        // Function to update the task list
        function updateTaskList() {
            const taskList = document.getElementById('task-list');
            taskList.innerHTML = '';

            tasks.forEach((task, index) => {
                const taskElement = document.createElement('div');
                taskElement.classList.add('task');

                taskElement.innerHTML = `
                    <p>${task.name}</p>
                    <span class="priority">${task.priority}</span>
                `;

                taskList.appendChild(taskElement);
            });
        }
    </script>
</body>
</html>
```



**Exercise 17: Expense Tracker:**

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Expense Tracker</title>
    <style>
        body {
            font-family: 'Arial', sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f5f5f5;
        }

        h1 {
            background-color: #3498db;
            color: #fff;
            padding: 20px;
            text-align: center;
            margin: 0;
        }

        #container {
            width: 80%;
            margin: 20px auto;
            background-color: #fff;
            border-radius: 10px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.2);
        }

        h2 {
            background-color: #3498db;
            color: #fff;
            padding: 10px;
            margin: 0;
        }

        #expense-list {
            padding: 20px;
            text-align: center;
        }

        .expense {
            display: flex;
            justify-content: space-between;
            align-items: center;
            background-color: #f2f2f2;
            border-radius: 5px;
            padding: 10px;
            margin-bottom: 10px;
            transition: background-color 0.3s;
        }

        .expense:hover {
            background-color: #e0e0e0;
        }

        .expense p {
            margin: 0;
            font-size: 18px;
        }

        .expense .amount {
            font-weight: bold;
            color: #3498db;
        }

        #add-expense-form {
            padding: 20px;
            background-color: #f2f2f2;
            border-radius: 0 0 10px 10px;
        }

        label {
            font-weight: bold;
            display: block;
        }

        input[type="text"], input[type="number"] {
            width: 100%;
            padding: 10px;
            margin-bottom: 10px;
            border: 1px solid #ccc;
            border-radius: 4px;
        }

        #add-expense-button {
            padding: 10px 20px;
            background-color: #3498db;
            color: #fff;
            border: none;
            border-radius: 5px;
            cursor: pointer;
        }

        #add-expense-button:hover {
            background-color: #2980b9;
        }
    </style>
</head>
<body>
    <h1>Expense Tracker</h1>
    <div id="container">
        <h2>Expense List</h2>
        <div id="expense-list">
            <!-- Expenses will be dynamically added here -->
        </div>
        <h2>Add Expense</h2>
        <div id="add-expense-form">
            <label for="expense-description">Description:</label>
            <input type="text" id="expense-description" placeholder="Enter description">
            <label for="expense-amount">Amount:</label>
            <input type="number" id="expense-amount" placeholder="Enter amount">
            <button id="add-expense-button" onclick="addExpense()">Add Expense</button>
        </div>
    </div>

    <script>
        // Object to store expenses
        const expenses = [];

        // Function to add an expense
        function addExpense() {
            const descriptionInput = document.getElementById('expense-description');
            const amountInput = document.getElementById('expense-amount');

            const description = descriptionInput.value;
            const amount = parseFloat(amountInput.value);

            if (!description || isNaN(amount) || amount <= 0) {
                alert('Please enter a valid description and amount.');
                return;
            }

            expenses.push({ description, amount });

            descriptionInput.value = '';
            amountInput.value = '';

            updateExpenseList();
        }

        // Function to update the expense list
        function updateExpenseList() {
            const expenseList = document.getElementById('expense-list');
            expenseList.innerHTML = '';

            expenses.forEach((expense, index) => {
                const expenseElement = document.createElement('div');
                expenseElement.classList.add('expense');

                expenseElement.innerHTML = `
                    <p>${expense.description}</p>
                    <p class="amount">$${expense.amount.toFixed(2)}</p>
                `;

                expenseList.appendChild(expenseElement);
            });
        }
    </script>
</body>
</html>
```




**Exercise 18: Fitness Tracker:**

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Fitness Tracker</title>
    <style>
        body {
            font-family: 'Arial', sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f5f5f5;
        }

        h1 {
            background-color: #f39c12;
            color: #fff;
            padding: 20px;
            text-align: center;
            margin: 0;
        }

        #container {
            width: 80%;
            margin: 20px auto;
            background-color: #fff;
            border-radius: 10px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.2);
        }

        h2 {
            background-color: #f39c12;
            color: #fff;
            padding: 10px;
            margin: 0;
        }

        #workout-list {
            padding: 20px;
        }

        .workout {
            display: flex;
            justify-content: space-between;
            align-items: center;
            background-color: #f2f2f2;
            border-radius: 5px;
            padding: 10px;
            margin-bottom: 10px;
            transition: background-color 0.3s;
        }

        .workout:hover {
            background-color: #e0e0e0;
        }

        .workout p {
            margin: 0;
            font-size: 18px;
        }

        .workout .duration {
            font-weight: bold;
            color: #f39c12;
        }

        #add-workout-form {
            padding: 20px;
        }

        label {
            font-weight: bold;
            display: block;
        }

        input[type="text"], input[type="number"] {
            width: 100%;
            padding: 10px;
            margin-bottom: 10px;
            border: 1px solid #ccc;
            border-radius: 4px;
        }

        #add-workout-button {
            padding: 10px 20px;
            background-color: #f39c12;
            color: #fff;
            border: none;
            border-radius: 5px;
            cursor: pointer;
        }

        #add-workout-button:hover {
            background-color: #e67e22;
        }
    </style>
</head>
<body>
    <h1>Fitness Tracker</h1>
    <div id="container">
        <h2>Workout List</h2>
        <div id="workout-list">
            <!-- Workouts will be dynamically added here -->
        </div>
        <h2>Add Workout</h2>
        <div id="add-workout-form">
            <label for="workout-name">Workout Name:</label>
            <input type="text" id="workout-name" placeholder="Enter workout name">
            <label for="workout-duration">Duration (minutes):</label>
            <input type="number" id="workout-duration" placeholder="Enter duration">
            <button id="add-workout-button" onclick="addWorkout()">Add Workout</button>
        </div>
    </div>

    <script>
        // Object to store workouts
        const workouts = [];

        // Function to add a workout
        function addWorkout() {
            const nameInput = document.getElementById('workout-name');
            const durationInput = document.getElementById('workout-duration');

            const name = nameInput.value;
            const duration = parseFloat(durationInput.value);

            if (!name || isNaN(duration) || duration <= 0) {
                alert('Please enter a valid workout name and duration.');
                return;
            }

            workouts.push({ name, duration });

            nameInput.value = '';
            durationInput.value = '';

            updateWorkoutList();
        }

        // Function to update the workout list
        function updateWorkoutList() {
            const workoutList = document.getElementById('workout-list');
            workoutList.innerHTML = '';

            workouts.forEach((workout, index) => {
                const workoutElement = document.createElement('div');
                workoutElement.classList.add('workout');

                workoutElement.innerHTML = `
                    <p>${workout.name}</p>
                    <p class="duration">${workout.duration} minutes</p>
                `;

                workoutList.appendChild(workoutElement);
            });
        }
    </script>
</body>
</html>
```







**Exercise 19: Contactless Payment System:**

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Contactless Payment System</title>
    <style>
        body {
            font-family: 'Arial', sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f7f7f7;
        }

        h1 {
            background-color: #e74c3c;
            color: #fff;
            padding: 20px;
            text-align: center;
            margin: 0;
        }

        #container {
            width: 80%;
            margin: 20px auto;
            background-color: #fff;
            border-radius: 10px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.2);
        }

        h2 {
            background-color: #e74c3c;
            color: #fff;
            padding: 10px;
            margin: 0;
        }

        #payment-history {
            padding: 20px;
        }

        .transaction {
            display: flex;
            justify-content: space-between;
            align-items: center;
            background-color: #f2f2f2;
            border-radius: 5px;
            padding: 10px;
            margin-bottom: 10px;
            transition: background-color 0.3s;
        }

        .transaction:hover {
            background-color: #e0e0e0;
        }

        .transaction p {
            margin: 0;
            font-size: 18px;
        }

        .transaction .amount {
            font-weight: bold;
            color: #e74c3c;
        }

        #add-payment-form {
            padding: 20px;
        }

        label {
            font-weight: bold;
            display: block;
        }

        input[type="text"], input[type="number"] {
            width: 100%;
            padding: 10px;
            margin-bottom: 10px;
            border: 1px solid #ccc;
            border-radius: 4px;
        }

        #add-payment-button {
            padding: 10px 20px;
            background-color: #e74c3c;
            color: #fff;
            border: none;
            border-radius: 5px;
            cursor: pointer;
        }

        #add-payment-button:hover {
            background-color: #c0392b;
        }
    </style>
</head>
<body>
    <h1>Contactless Payment System</h1>
    <div id="container">
        <h2>Payment History</h2>
        <div id="payment-history">
            <!-- Payment transactions will be dynamically added here -->
        </div>
        <h2>Make Payment</h2>
        <div id="add-payment-form">
            <label for="card-number">Card Number:</label>
            <input type="text" id="card-number" placeholder="Enter card number">
            <label for="amount">Amount (USD):</label>
            <input type="number" id="amount" placeholder="Enter amount">
            <button id="add-payment-button" onclick="makePayment()">Make Payment</button>
        </div>
    </div>

    <script>
        // Object to store payment history
        const paymentHistory = [];

        // Function to make a payment
        function makePayment() {
            const cardNumberInput = document.getElementById('card-number');
            const amountInput = document.getElementById('amount');

            const cardNumber = cardNumberInput.value;
            const amount = parseFloat(amountInput.value);

            if (!cardNumber || isNaN(amount) || amount <= 0) {
                alert('Please enter a valid card number and amount.');
                return;
            }

            const transaction = {
                cardNumber,
                amount
            };

            paymentHistory.push(transaction);

            cardNumberInput.value = '';
            amountInput.value = '';

            updatePaymentHistory();
        }

        // Function to update the payment history
        function updatePaymentHistory() {
            const paymentHistoryList = document.getElementById('payment-history');
            paymentHistoryList.innerHTML = '';

            paymentHistory.forEach((transaction, index) => {
                const transactionElement = document.createElement('div');
                transactionElement.classList.add('transaction');

                transactionElement.innerHTML = `
                    <p>Card Number: ${transaction.cardNumber}</p>
                    <p class="amount">$${transaction.amount.toFixed(2)}</p>
                `;

                paymentHistoryList.appendChild(transactionElement);
            });
        }
    </script>
</body>
</html>
```



**Exercise 20: Employee Performance Evaluation:**

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Employee Performance Evaluation</title>
    <style>
        body {
            font-family: 'Arial', sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f7f7f7;
        }

        h1 {
            background-color: #3498db;
            color: #fff;
            padding: 20px;
            text-align: center;
            margin: 0;
        }

        #container {
            width: 80%;
            margin: 20px auto;
            background-color: #fff;
            border-radius: 10px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.2);
        }

        h2 {
            background-color: #3498db;
            color: #fff;
            padding: 10px;
            margin: 0;
        }

        #employee-list {
            padding: 20px;
        }

        .employee {
            display: flex;
            justify-content: space-between;
            align-items: center;
            background-color: #f2f2f2;
            border-radius: 5px;
            padding: 10px;
            margin-bottom: 10px;
            transition: background-color 0.3s;
        }

        .employee:hover {
            background-color: #e0e0e0;
        }

        .employee p {
            margin: 0;
            font-size: 18px;
        }

        .employee .performance {
            font-weight: bold;
            color: #3498db;
        }

        #add-employee-form {
            padding: 20px;
        }

        label {
            font-weight: bold;
            display: block;
        }

        input[type="text"], input[type="number"] {
            width: 100%;
            padding: 10px;
            margin-bottom: 10px;
            border: 1px solid #ccc;
            border-radius: 4px;
        }

        #add-employee-button {
            padding: 10px 20px;
            background-color: #3498db;
            color: #fff;
            border: none;
            border-radius: 5px;
            cursor: pointer;
        }

        #add-employee-button:hover {
            background-color: #2980b9;
        }

        #generate-report-button {
            padding: 10px 20px;
            background-color: #e74c3c;
            color: #fff;
            border: none;
            border-radius: 5px;
            cursor: pointer;
        }

        #generate-report-button:hover {
            background-color: #c0392b;
        }
    </style>
</head>
<body>
    <h1>Employee Performance Evaluation</h1>
    <div id="container">
        <h2>Employee List</h2>
        <div id="employee-list">
            <!-- Employees will be dynamically added here -->
        </div>
        <h2>Add Employee</h2>
        <div id="add-employee-form">
            <label for="employee-name">Employee Name:</label>
            <input type="text" id="employee-name" placeholder="Enter employee name">
            <label for="employee-performance">Performance (1-10):</label>
            <input type="number" id="employee-performance" placeholder="Enter performance rating">
            <button id="add-employee-button" onclick="addEmployee()">Add Employee</button>
        </div>
        <h2>Generate Performance Report</h2>
        <button id="generate-report-button" onclick="generateReport()">Generate Report</button>
    </div>

    <script>
        // Object to store employee data
        const employees = [];

        // Function to add an employee
        function addEmployee() {
            const nameInput = document.getElementById('employee-name');
            const performanceInput = document.getElementById('employee-performance');

            const name = nameInput.value;
            const performance = parseInt(performanceInput.value);

            if (!name || isNaN(performance) || performance < 1 || performance > 10) {
                alert('Please enter a valid employee name and performance rating between 1 and 10.');
                return;
            }

            employees.push({ name, performance });

            nameInput.value = '';
            performanceInput.value = '';

            updateEmployeeList();
        }

        // Function to update the employee list
        function updateEmployeeList() {
            const employeeList = document.getElementById('employee-list');
            employeeList.innerHTML = '';

            employees.forEach((employee, index) => {
                const employeeElement = document.createElement('div');
                employeeElement.classList.add('employee');

                employeeElement.innerHTML = `
                    <p>${employee.name}</p>
                    <p class="performance">Performance: ${employee.performance}</p>
                `;

                employeeList.appendChild(employeeElement);
            });
        }

        // Function to generate a performance report
        function generateReport() {
            const totalEmployees = employees.length;
            if (totalEmployees === 0) {
                alert('No employees to generate a report.');
                return;
            }

            let totalPerformance = 0;
            employees.forEach((employee) => {
                totalPerformance += employee.performance;
            });

            const averagePerformance = (totalPerformance / totalEmployees).toFixed(2);

            alert(`Performance Report\n\nTotal Employees: ${totalEmployees}\nAverage Performance: ${averagePerformance}`);
        }
    </script>
</body>
</html>
```
