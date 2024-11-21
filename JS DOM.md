# Document Object Model (DOM)

## 📘 Introduction to DOM

The **Document Object Model (DOM)** is a programming interface for HTML and XML documents. It represents the structure of a document as a tree of objects, where each object represents a part of the document, such as an element, attribute, or text.

### 🔑 Key Characteristics of DOM
- Represents HTML/XML documents as a hierarchical tree structure
- Allows JavaScript to dynamically access and modify document content
- Provides methods to create, change, and remove HTML elements and attributes

## 🌳 DOM Tree Structure

### Document Tree Representation
```
document
│
└── html
    ├── head
    │   └── various metadata elements
    └── body
        └── various HTML elements
```

### 📋 DOM Collections
- `getElementsByTagName()`: Returns a collection of elements with a specific tag
- `getElementsByClassName()`: Returns elements with a specific class name
- `querySelectorAll()`: Returns all elements matching a CSS selector

## 🎯 Event Handling in DOM

### 📝 addEventListener Syntax
```javascript
element.addEventListener(event, function, useCapture);
```

#### Parameters
- `element`: The DOM element
- `event`: Type of event (e.g., 'click', 'blur')
- `function`: Callback function to execute
- `useCapture`: Optional boolean for event phase (default: false)

### 🖱️ Common Events

#### Mouse Events
- `click`: Triggered when an element is clicked
- `mouseover`: When mouse enters an element
- `mouseout`: When mouse leaves an element
- `mousemove`: When mouse moves over an element

#### 📋 Form Events
- `focus`: When an element receives focus
- `blur`: When an element loses focus
- `submit`: When a form is submitted
- `reset`: When a form is reset
- `change`: When element value changes

## 💡 Simple Event Handling Examples

### 1. Click Event
```html
<!DOCTYPE html>
<html>
<body>
    <button id="myButton">Click Me!</button>
    <p id="demo"></p>

    <script>
        const button = document.getElementById('myButton');
        button.addEventListener('click', function() {
            document.getElementById("demo").innerHTML = "Button Clicked!";
        });
    </script>
</body>
</html>
```

### 2. Focus and Blur Events
```html
<!DOCTYPE html>
<html>
<body>
    <input type="text" id="myInput">
    <p id="message"></p>

    <script>
        const input = document.getElementById('myInput');
        input.addEventListener('focus', function() {
            input.style.backgroundColor = "yellow";
        });
        
        input.addEventListener('blur', function() {
            input.style.backgroundColor = "white";
            document.getElementById('message').textContent = input.value.toUpperCase();
        });
    </script>
</body>
</html>
```

## 🎨 Dynamic Styling and Animations

### Using setInterval() for Animations
```javascript
// Change text color every second
// Change text color every second
const interval = setInterval(() => {
  const text = document.getElementById('text');
  text.style.color = text.style.color === 'red' ? 'green' : 'red';
}, 1000);

// Stop after 10 seconds
setTimeout(() => clearInterval(interval), 10000);
```

## 🔄 Event Bubbling

Event bubbling is a propagation mechanism where an event triggered on a nested element "bubbles up" through its parent elements.

```html
<!DOCTYPE html>
<html>
<body>
    <div id="parent">
        <button id="child">Click me</button>
    </div>

    <script>
        document.getElementById('parent').addEventListener('click', function() {
            console.log('Parent div clicked');
        });

        document.getElementById('child').addEventListener('click', function() {
            console.log('Child button clicked');
        });
        // Clicking the button will trigger both event listeners
    </script>
</body>
</html>
```

## 🛠️ Manipulating DOM Elements

### Adding and Removing Elements
```javascript
// Create a new element
let newElement = document.createElement('div');
newElement.textContent = 'New Element';
document.body.appendChild(newElement);

// Remove an element
document.body.removeChild(newElement);
```
