# CSS Styling Guide

## Types of CSS

### 1. Inline CSS
```html
<div style="color: blue; font-size: 16px;">
  Directly applied to an element
</div>
```

### 2. Internal CSS
```html
<style>
  body {
    background-color: #f4f4f4;
  }
  h1 {
    color: navy;
  }
</style>
```

### 3. External CSS
```html
<link rel="stylesheet" href="styles.css">
```
`styles.css`:
```css
body {
  font-family: Arial, sans-serif;
}
```

## Conflicting Style Sheets

### Cascading Priority
1. Inline Styles (Highest Priority)
2. Internal Stylesheets
3. External Stylesheets
4. Browser Default Styles

### Specificity Hierarchy
```css
/* Less Specific */
div { color: blue; }

/* More Specific */
.class-name { color: red; }

/* Most Specific */
#unique-id { color: green; }
```

## Positioning Elements

### Position Types
```css
.static { 
  position: static; /* Default */
}

.relative {
  position: relative;
  top: 20px;
  left: 30px;
}

.absolute {
  position: absolute;
  top: 50px;
  right: 0;
}

.fixed {
  position: fixed;
  bottom: 0;
  right: 0;
}

.sticky {
  position: sticky;
  top: 0;
}
```

## Element Dimensions

### Width and Height
```css
.element {
  width: 300px;
  height: 200px;
  max-width: 500px;
  min-height: 100px;
}

/* Responsive */
.responsive {
  width: 100%;
  max-width: 600px;
}
```

## Box Model

### Standard Box Model
```css
.box-model {
  width: 300px;
  padding: 20px;
  border: 5px solid black;
  margin: 10px;
}

/* Change box-sizing */
* {
  box-sizing: border-box;
}
```

### Box Model Components
- Content
- Padding
- Border
- Margin

## Text Flow

### Text Formatting
```css
.text-flow {
  text-align: center;
  text-decoration: underline;
  line-height: 1.6;
  letter-spacing: 1px;
  word-spacing: 2px;
}
```

## Drop-Down Menus

### Basic Dropdown
```css
.dropdown {
  position: relative;
  display: inline-block;
}

.dropdown-content {
  display: none;
  position: absolute;
  background-color: #f9f9f9;
  min-width: 160px;
  box-shadow: 0px 8px 16px 0px rgba(0,0,0,0.2);
}

.dropdown:hover .dropdown-content {
  display: block;
}
```

## Text Shadows

### Shadow Variations
```css
.text-shadow {
  /* offset-x | offset-y | blur-radius | color */
  text-shadow: 2px 2px 4px #000000;
  
  /* Multiple shadows */
  text-shadow: 
    1px 1px 2px red,
    0 0 1em blue;
}
```

## Rounded Corners

### Border Radius
```css
.rounded {
  border-radius: 10px; /* All corners */
  
  /* Individual corners */
  border-top-left-radius: 10px;
  border-top-right-radius: 20px;
  border-bottom-right-radius: 30px;
  border-bottom-left-radius: 40px;
}

/* Elliptical corners */
.elliptical {
  border-radius: 50% / 20%;
}
```

## Color Styling

### Color Types
```css
.color-types {
  /* Named colors */
  color: red;
  
  /* Hex */
  background-color: #FF0000;
  
  /* RGB */
  border-color: rgb(255, 0, 0);
  
  /* RGBA (with opacity) */
  background: rgba(255, 0, 0, 0.5);
  
  /* HSL */
  color: hsl(0, 100%, 50%);
  
  /* HSLA */
  background: hsla(0, 100%, 50%, 0.7);
}
```

## Box Shadows

### Shadow Techniques
```css
.box-shadow {
  /* Basic shadow */
  box-shadow: 5px 5px 10px rgba(0,0,0,0.3);
  
  /* Inset shadow */
  box-shadow: inset 0 0 10px rgba(0,0,0,0.5);
  
  /* Multiple shadows */
  box-shadow: 
    3px 3px 5px rgba(0,0,0,0.3),
    -3px -3px 5px rgba(0,0,0,0.2);
}
```

