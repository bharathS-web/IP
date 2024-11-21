# HTML5

### Editing HTML
- Use any text editor (Notepad, VS Code, Sublime Text)
- Save files with `.html` extension
- Basic structure:
  ```html
  <!DOCTYPE html>
  <html lang="en">
  <head>
    <meta charset="UTF-8">
    <title>Page Title</title>
  </head>
  <body>
    <!-- Content goes here -->
  </body>
  </html>
  ```

### W3C HTML Validation
- Official validation service: https://validator.w3.org/
- Checks HTML for errors and compliance
- Helps ensure cross-browser compatibility

## HTML5 Elements and Structure

### Headings
```html
<h1>Main Heading</h1>
<h2>Subheading</h2>
<h3>Sub-subheading</h3>
<h4>Smaller Heading</h4>
<h5>Even Smaller Heading</h5>
<h6>Smallest Heading</h6>
```

### Linking
#### External Linking
```html
<a href="https://www.example.com">Visit Example Website</a>
```

#### Internal Linking
```html
<!-- Link to another page in same site -->
<a href="about.html">About Us</a>

<!-- Link to specific section on same page -->
<a href="#section1">Go to Section 1</a>
<div id="section1">Section 1 Content</div>
```

### Images
```html
<img src="image.jpg" alt="Description of image" width="300" height="200">
```

### Special Characters
```html
&copy;   <!-- Copyright symbol -->
&reg;    <!-- Registered trademark -->
&trade;  <!-- Trademark symbol -->
&nbsp;   <!-- Non-breaking space -->
```

### Horizontal Rule
```html
<hr>  <!-- Horizontal line separator -->
```

## Lists

## Ordered Lists (Numbered Lists)

### Numeric Numbering
```html
<ol>
  <li>First item</li>
  <li>Second item</li>
  <li>Third item</li>
</ol>
```
Output: 1. 2. 3.

### Lowercase Alphabetic
```html
<ol type="a">
  <li>First item</li>
  <li>Second item</li>
  <li>Third item</li>
</ol>
```
Output: a. b. c.

### Uppercase Alphabetic
```html
<ol type="A">
  <li>First item</li>
  <li>Second item</li>
  <li>Third item</li>
</ol>
```
Output: A. B. C.

### Lowercase Roman Numerals
```html
<ol type="i">
  <li>First item</li>
  <li>Second item</li>
  <li>Third item</li>
</ol>
```
Output: i. ii. iii.

### Uppercase Roman Numerals
```html
<ol type="I">
  <li>First item</li>
  <li>Second item</li>
  <li>Third item</li>
</ol>
```
Output: I. II. III.

### Starting from a Specific Number
```html
<ol start="5">
  <li>First item</li>
  <li>Second item</li>
  <li>Third item</li>
</ol>
```
Output: 5. 6. 7.

## Unordered Lists (Bullet Lists)

### Default Bullets
```html
<ul>
  <li>First item</li>
  <li>Second item</li>
  <li>Third item</li>
</ul>
```

### Disc (Default)
```html
<ul type="disc">
  <li>First item</li>
  <li>Second item</li>
  <li>Third item</li>
</ul>
```

### Circle Bullets
```html
<ul type="circle">
  <li>First item</li>
  <li>Second item</li>
  <li>Third item</li>
</ul>
```

### Square Bullets
```html
<ul type="square">
  <li>First item</li>
  <li>Second item</li>
  <li>Third item</li>
</ul>
```

## Nested Lists
```html
<ol>
  <li>First main item
    <ul>
      <li>Subitem 1</li>
      <li>Subitem 2</li>
    </ul>
  </li>
  <li>Second main item
    <ol type="a">
      <li>Nested alphabetic item</li>
      <li>Another nested item</li>
    </ol>
  </li>
</ol>
```

 
## Tables
```html
<table>
  <thead>
    <tr>
      <th>Header 1</th>
      <th>Header 2</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Row 1, Cell 1</td>
      <td>Row 1, Cell 2</td>
    </tr>
  </tbody>
</table>
```

## Forms

### Basic Form Structure
```html
<form action="/submit" method="post">
  <label for="name">Name:</label>
  <input type="text" id="name" name="name" required>
  
  <label for="email">Email:</label>
  <input type="email" id="email" name="email" required>
  
  <input type="submit" value="Submit">
</form>
```

## HTML5 Form Input Types
```html
<input type="button">
<input type="checkbox">
<input type="color">
<input type="date">
<input type="datetime-local">
<input type="email">
<input type="file">
<input type="hidden">
<input type="image">
<input type="month">
<input type="number">
<input type="password">
<input type="radio">
<input type="range">
<input type="reset">
<input type="search">
<input type="submit">
<input type="tel">
<input type="text">
<input type="time">
<input type="url">
<input type="week">
```

### Datalist with Autocomplete
```html
<input list="browsers" name="browser">
<datalist id="browsers">
  <option value="Chrome">
  <option value="Firefox">
  <option value="Safari">
</datalist>
```

## Page Structure Elements

### Semantic HTML5 Elements
```html
<header>Page or section header</header>
<nav>Navigation menu</nav>
<main>Main content of page</main>
<article>Independent, self-contained content</article>
<section>Thematic grouping of content</section>
<aside>Side content related to surrounding content</aside>
<footer>Page or section footer</footer>
```

## Meta Elements
```html
<head>
  <meta charset="UTF-8">
  <meta name="description" content="Page description">
  <meta name="keywords" content="HTML, CSS, JavaScript">
  <meta name="author" content="Your Name">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
</head>
```

## Best Practices
- Always use semantic HTML
- Validate your HTML
- Use appropriate meta tags
- Ensure accessibility
- Keep code clean and well-structured
