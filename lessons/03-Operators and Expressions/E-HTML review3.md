---
title: "HTML Review 3"
description: "HTML Review 3"
---

### 1. **Tables (`<table>`, `<tr>`, `<th>`, `<td>`):**
Tables are used to display data in a structured way. Here's a simple example:

```html
<table border="1">
    <tr>
        <th>Header 1</th>
        <th>Header 2</th>
    </tr>
    <tr>
        <td>Row 1, Cell 1</td>
        <td>Row 1, Cell 2</td>
    </tr>
    <tr>
        <td>Row 2, Cell 1</td>
        <td>Row 2, Cell 2</td>
    </tr>
</table>
```

- `<table>`: Defines a table.
- `<tr>`: Defines a table row.
- `<th>`: Defines a table header (typically for the first row).
- `<td>`: Defines a table cell.

### 2. **Semantic Elements:**
HTML5 introduced semantic elements that provide meaning to the structure. Examples include `<header>`, `<nav>`, `<article>`, `<section>`, `<footer>`, etc. They make your HTML more readable and help search engines understand the content better.

```html
<header>
    <h1>Website Title</h1>
</header>

<nav>
    <ul>
        <li><a href="#">Home</a></li>
        <li><a href="#">About</a></li>
        <li><a href="#">Contact</a></li>
    </ul>
</nav>

<section>
    <h2>Main Content Section</h2>
    <p>This is the main content of the page.</p>
</section>

<aside>
    <h2>Side Content</h2>
    <p>Additional information or links can go here.</p>
</aside>

<footer>
    <p>&copy; 2023 Your Website</p>
</footer>
```

### 3. **Comments (`<!-- ... -->`):**
You can add comments to your HTML code to provide explanations or reminders. Comments are not displayed in the browser.

```html
<!-- This is a comment -->
<p>This is a paragraph.</p>
```

Comments are useful for documenting your code, especially when working in a team or coming back to your code after some time.
