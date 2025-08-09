## 🧠 What is the DOM?

- The **DOM (Document Object Model)** is a programming interface for HTML and XML documents.
    
- It represents the structure of a document as a tree of **nodes**.
    
- Each element, attribute, and text in an HTML page is a node.
    

> JavaScript can read and manipulate the DOM to dynamically change the content, structure, and style of a web page.

---

## 🌳 DOM Tree Structure

HTML Code:

```html
<!DOCTYPE html>
<html>
  <head>
    <title>Example</title>
  </head>
  <body>
    <h1>Hello</h1>
    <p>This is a paragraph.</p>
  </body>
</html>
```

DOM Representation:

```
Document
└── html
    ├── head
    │   └── title
    └── body
        ├── h1
        └── p
```

---

## 🔍 Accessing DOM Elements

### `getElementById()`

```js
const title = document.getElementById("myTitle");
```

### `getElementsByClassName()`

```js
const items = document.getElementsByClassName("list-item");
```

### `getElementsByTagName()`

```js
const paragraphs = document.getElementsByTagName("p");
```

### `querySelector()` / `querySelectorAll()`

```js
const firstItem = document.querySelector(".list-item");
const allItems = document.querySelectorAll(".list-item");
```

---

## ✏️ Modifying Elements

### Changing text content

```js
document.getElementById("header").textContent = "New Header Text";
```

### Changing HTML content

```js
document.getElementById("content").innerHTML = "<strong>Bold text</strong>";
```

### Changing style

```js
const box = document.getElementById("box");
box.style.backgroundColor = "blue";
box.style.color = "white";
```

---

## ➕ Creating and Removing Elements

### Create Element

```js
const newParagraph = document.createElement("p");
newParagraph.textContent = "This is a new paragraph.";
document.body.appendChild(newParagraph);
```

### Remove Element

```js
const oldElement = document.getElementById("old");
oldElement.remove();
```

---

## 🧩 Working with Attributes and Classes

### Attributes

```js
const img = document.querySelector("img");
img.setAttribute("src", "image.jpg");
console.log(img.getAttribute("src"));
img.removeAttribute("alt");
```

### Classes

```js
const button = document.getElementById("btn");
button.classList.add("active");
button.classList.remove("inactive");
button.classList.toggle("highlight");
```

---

## 🖱️ Event Handling

### Basic Syntax

```js
const btn = document.getElementById("clickMe");
btn.addEventListener("click", function() {
  alert("Button clicked!");
});
```

### With named function

```js
function greetUser() {
  alert("Hello user!");
}
btn.addEventListener("click", greetUser);
```

---

## ⌨️ Common Events

- `click`
    
- `mouseover` / `mouseout`
    
- `keydown` / `keyup`
    
- `submit`
    
- `change`
    
- `input`
    

Example:

```js
const input = document.getElementById("username");
input.addEventListener("input", (e) => {
  console.log("You typed:", e.target.value);
});
```

---

## 💻 Mini Project Example

HTML:

```html
<input type="text" id="nameInput" placeholder="Enter your name">
<button id="greetBtn">Greet Me</button>
<p id="greeting"></p>
```

JavaScript:

```js
const input = document.getElementById("nameInput");
const button = document.getElementById("greetBtn");
const greeting = document.getElementById("greeting");

button.addEventListener("click", () => {
  const name = input.value.trim();
  greeting.textContent = name ? `Hello, ${name}!` : "Please enter your name.";
});
```

---

## ✅ Best Practices

- Always **cache selectors** (store them in variables) if reused.
    
- Use `textContent` instead of `innerHTML` when inserting plain text.
    
- Avoid direct style manipulation — prefer using CSS classes.
    
- Always validate input before using `.value`.
    
- Use `addEventListener` instead of inline event attributes (like `onclick`).
    

---
