---
title: "HTML Review 2"
description: "HTML Review 2"
---


1. **Links (`<a>`):** Used to create hyperlinks. The `href` attribute contains the URL of the link.

   ```html
   <a href="https://www.example.com">Visit our website</a>
   ```

2. **Images (`<img>`):** Used to embed images. The `src` attribute contains the path to the image file.

   ```html
   <img src="image.jpg" alt="Description of the image">
   ```

3. **Lists (`<ul>`, `<ol>`, `<li>`):** Used to create unordered and ordered lists.

   ```html
   <ul>
       <li>Item 1</li>
       <li>Item 2</li>
   </ul>

   <ol>
       <li>First</li>
       <li>Second</li>
   </ol>
   ```

4. **Forms (`<form>`, `<input>`, `<button>`):** Used for user input. The `action` attribute in the `<form>` tag specifies where to send the form data.

   ```html
   <form action="/submit" method="post">
       <label for="username">Username:</label>
       <input type="text" id="username" name="username">

       <label for="password">Password:</label>
       <input type="password" id="password" name="password">

       <button type="submit">Submit</button>
   </form>
   ```

5. **Divisions (`<div>`):** Acts as a container for other HTML elements. It's often used to group elements and apply styles.

   ```html
   <div>
       <p>This is a paragraph inside a division.</p>
       <img src="image.jpg" alt="An image inside a division">
   </div>
   ```

