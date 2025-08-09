## 📘 What is Express.js?

**Express.js** is a **minimal and flexible web application framework** for **Node.js** that simplifies building web servers and APIs.

It provides a robust set of features for:

- Routing
    
- Middleware
    
- Rendering views
    
- Handling requests and responses
    

> Think of Express as a lightweight layer on top of Node.js's built-in `http` module.

---

## 🧱 Why Use Express?

- ✅ Simplifies HTTP server creation
    
- ✅ Built-in routing system
    
- ✅ Middleware support (logging, parsing, authentication, etc.)
    
- ✅ Easy integration with view engines like EJS
    
- ✅ Massive ecosystem and community
    

---

## 🛠️ Installing Express

```bash
npm install express
```

Create a file called `app.js`:

```js
const express = require('express');
const app = express();

app.get('/', (req, res) => {
  res.send('Hello World!');
});

app.listen(3000, () => {
  console.log('Server is running on http://localhost:3000');
});
```

Run your server:

```bash
node app.js
```

Open your browser and go to [http://localhost:3000](http://localhost:3000/)

---

## 📥 Handling Requests

### Basic HTTP Methods

```js
app.get('/', (req, res) => {
  res.send('GET request');
});

app.post('/', (req, res) => {
  res.send('POST request');
});

app.put('/', (req, res) => {
  res.send('PUT request');
});

app.delete('/', (req, res) => {
  res.send('DELETE request');
});
```

---

## 🗂️ Basic Routing

```js
app.get('/about', (req, res) => {
  res.send('About Page');
});

app.get('/users/:id', (req, res) => {
  const userId = req.params.id;
  res.send(`User ID: ${userId}`);
});
```

### Query Parameters

```js
app.get('/search', (req, res) => {
  const query = req.query.q;
  res.send(`Search query: ${query}`);
});
```

---

## 🧩 Middleware Basics

Middleware functions are functions that have access to the request and response objects.

### Example: Logger Middleware

```js
app.use((req, res, next) => {
  console.log(`${req.method} ${req.url}`);
  next();
});
```

Use built-in middleware:

```js
app.use(express.static('public'));      // serve static files
app.use(express.json());                // parse JSON bodies
app.use(express.urlencoded({ extended: true })); // parse URL-encoded bodies
```

---

## 📄 Sending Responses

- `res.send()` – send a string or object
    
- `res.json()` – send a JSON response
    
- `res.render()` – render a view template (like EJS)
    
- `res.status()` – set status code
    

Example:

```js
res.status(404).send('Page not found');
```

---

## ✅ Summary

- Express.js is a powerful, minimalist web framework for Node.js
    
- It simplifies request handling, routing, and middleware
    
- Great for building web servers and RESTful APIs
    
- Easy to extend and integrate with other tools like EJS
    

---
