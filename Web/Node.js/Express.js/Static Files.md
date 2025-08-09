## 📘 What Are Static Files?

**Static files** include assets like:

- HTML files
    
- CSS stylesheets
    
- JavaScript scripts (client-side)
    
- Images (PNG, JPG, SVG)
    
- Fonts, videos, etc.
    

These files do **not change dynamically** and are served as-is to the client.

---

## 🛠️ Serving Static Files with Express

Express provides built-in middleware `express.static` to serve static files from a directory.

### Example:

```js
const express = require('express');
const app = express();

// Serve static files from the "public" folder
app.use(express.static('public'));

app.listen(3000, () => {
  console.log('Server running on http://localhost:3000');
});
```

### Folder structure:

```
project/
├── app.js
└── public/
    ├── index.html
    ├── styles.css
    └── script.js
```

Now, visiting `http://localhost:3000/index.html` serves the HTML file.

---

## 📁 Setting a Virtual Path Prefix

You can use a virtual path prefix to serve files under a specific route:

```js
app.use('/static', express.static('public'));
```

Now files are available at:

```
http://localhost:3000/static/index.html
```

---

## 🧠 Multiple Static Directories

You can serve multiple directories:

```js
app.use(express.static('public'));
app.use(express.static('assets'));
```

If a file is found in both, the first directory takes priority.

---

## ❌ Handling 404 for Missing Static Files

Static file requests that don’t match will **not** throw errors. If needed, you can add a catch-all handler:

```js
app.use((req, res) => {
  res.status(404).send('File Not Found');
});
```

---

## ✅ Summary

- Use `express.static()` to serve static files like HTML, CSS, and JS
    
- Default behavior maps URL paths to file names
    
- Add a virtual prefix or serve multiple folders
    
- Place this middleware **early** in the stack (before route handlers)
    

---
