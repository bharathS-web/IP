# JavaScript 

## Introduction to JavaScript
JavaScript is a high-level, interpreted programming language primarily used for web development. It allows you to create dynamic and interactive web pages.

## Basic Syntax
```javascript
// Single-line comment
/* Multi-line
   comment */

// Basic statement
console.log("Hello, World!");
```

## Variables and Data Types

### Variable Declarations
```javascript
// var (function-scoped, legacy)
var oldVariable = "Old way";

// let (block-scoped, recommended)
let blockVariable = "Modern declaration";

// const (constant, cannot be reassigned)
const PI = 3.14159;
```

### Data Types
```javascript
// Primitive Types
let numberType = 42;           // Number
let stringType = "JavaScript"; // String
let booleanType = true;        // Boolean
let undefinedType;             // Undefined
let nullType = null;           // Null
let symbolType = Symbol("unique"); // Symbol

// Complex Type
let objectType = { 
  name: "JavaScript", 
  year: 1995 
};
```

## Control Statements

### Conditional Statements
```javascript
// If-Else
if (condition) {
  // Code to execute if true
} else {
  // Code to execute if false
}

// Switch Statement
switch (expression) {
  case value1:
    // Code block
    break;
  case value2:
    // Code block
    break;
  default:
    // Default code block
}
```

### Loops
```javascript
// For Loop
for (let i = 0; i < 5; i++) {
  console.log(i);
}

// While Loop
let j = 0;
while (j < 5) {
  console.log(j);
  j++;
}

// Do-While Loop
do {
  console.log(j);
  j++;
} while (j < 10);
```

## Operators

### Arithmetic Operators
```javascript
let a = 10;
let b = 5;

console.log(a + b);  // Addition
console.log(a - b);  // Subtraction
console.log(a * b);  // Multiplication
console.log(a / b);  // Division
console.log(a % b);  // Modulus
console.log(a ** b); // Exponentiation
```

### Comparison Operators
```javascript
console.log(5 == "5");   // Loose equality (value)
console.log(5 === "5");  // Strict equality (type and value)
console.log(5 != "5");   // Loose inequality
console.log(5 !== "5");  // Strict inequality
```

### Logical Operators
```javascript
let x = true;
let y = false;

console.log(x && y);  // AND
console.log(x || y);  // OR
console.log(!x);      // NOT
```

## Literals
```javascript
// Numeric Literal
let age = 30;

// String Literal
let greeting = "Hello, World!";

// Array Literal
let fruits = ["Apple", "Banana", "Cherry"];

// Object Literal
let person = {
  name: "John",
  age: 30,
  city: "New York"
};
```

## Functions

### Function Declarations
```javascript
// Traditional Function
function greet(name) {
  return `Hello, ${name}!`;
}

// Arrow Function
const multiply = (a, b) => a * b;

// Function with Default Parameter
function power(base, exponent = 2) {
  return Math.pow(base, exponent);
}
```

## Objects

### Object Creation
```javascript
// Object Literal
let car = {
  brand: "Toyota",
  model: "Camry",
  year: 2022,
  start: function() {
    console.log("Engine started");
  }
};

// Using Constructor
class Person {
  constructor(name, age) {
    this.name = name;
    this.age = age;
  }

  introduce() {
    console.log(`I'm ${this.name}`);
  }
}

let john = new Person("John", 30);
```

## Arrays

### Array Methods
```javascript
let numbers = [1, 2, 3, 4, 5];

// Adding/Removing Elements
numbers.push(6);     // Add to end
numbers.pop();       // Remove from end
numbers.unshift(0);  // Add to beginning
numbers.shift();     // Remove from beginning

// Transformation
let doubled = numbers.map(num => num * 2);
let evens = numbers.filter(num => num % 2 === 0);
```

## Built-in Objects

### Math Object
```javascript
console.log(Math.random());    // Random number
console.log(Math.floor(4.7));  // Round down
console.log(Math.ceil(4.1));   // Round up
console.log(Math.max(1, 5, 3)); // Maximum value
```

### Date Object
```javascript
let currentDate = new Date();
console.log(currentDate.getFullYear());
console.log(currentDate.getMonth());
console.log(currentDate.getDate());
```
