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

