## 📘 What is EJS?

**EJS (Embedded JavaScript)** is a templating engine that lets you generate HTML markup with plain JavaScript.

- File extension: `.ejs`
    
- Allows dynamic content rendering using JavaScript variables
    
- Useful in server-rendered Node.js applications (e.g., with Express.js)
    

### 🔧 Installing EJS

```bash
npm install ejs
```

In your Express app:

```js
app.set('view engine', 'ejs');
```

By default, Express looks for templates inside a `views/` directory.

---

## 🖼️ Views in EJS

Views are EJS templates rendered by the server and sent to the client as HTML.

### 📄 Example: `views/index.ejs`

```ejs
<!DOCTYPE html>
<html>
<head>
  <title>Home</title>
</head>
<body>
  <h1>Welcome, <%= username %>!</h1>
</body>
</html>
```

### 🧠 Rendering a View in Express

```js
app.get('/', (req, res) => {
  res.render('index', { username: 'Alice' });
});
```

- `<%= %>`: Output the value and escape it
    
- `<%- %>`: Output raw, unescaped HTML
    
- `<% %>`: Run JavaScript code (no output)
    

---

## 🧩 Partials in EJS

Partials are reusable chunks of templates (like headers, footers, navigation bars).

### 📁 Example Structure:

```
views/
├── partials/
│   ├── header.ejs
│   └── footer.ejs
├── index.ejs
```

### 🔁 Using Partials

You include them with `<%- include() %>`:

```ejs
<%- include('partials/header') %>
<h1>Welcome!</h1>
<%- include('partials/footer') %>
```

> ⚠️ Don't forget to use `<%- %>` to render raw HTML from the partial.

---

## 🧱 Layouts with EJS (Using ejs-mate or express-ejs-layouts)

EJS does not support layouts out of the box. You can use libraries like:

### Option 1: `ejs-mate`

```bash
npm install ejs-mate
```

In your app:

```js
const engine = require('ejs-mate');
app.engine('ejs', engine);
```

### Layout Example

#### `views/layouts/main.ejs`

```ejs
<!DOCTYPE html>
<html>
<head>
  <title><%- title %></title>
</head>
<body>
  <%- body %>
</body>
</html>
```

#### `views/index.ejs`

```ejs
<% layout('layouts/main') -%>
<h1>Home Page</h1>
```

### Option 2: `express-ejs-layouts`

```bash
npm install express-ejs-layouts
```

In your app:

```js
const expressLayouts = require('express-ejs-layouts');
app.use(expressLayouts);
app.set('layout', 'layouts/main');
```

Use `layout.ejs` like in `ejs-mate`, but it works automatically.

---

## ✅ Summary

- **EJS** allows embedding JavaScript in HTML
    
- **Views** render pages using data from the server
    
- **Partials** make templates DRY by reusing HTML chunks
    
- **Layouts** define consistent outer structure across pages (with `ejs-mate` or `express-ejs-layouts`)
    

---
