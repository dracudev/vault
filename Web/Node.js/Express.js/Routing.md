## 📘 What is Routing?

**Routing** in Express.js refers to how an application’s endpoints (URIs) respond to client requests.

- Each route defines a **path** and an **HTTP method** (`GET`, `POST`, `PUT`, `DELETE`, etc.)
    
- Routes can be simple or dynamic (with parameters)
    

---

## 🔧 Basic Route Definition

```js
app.get('/', (req, res) => {
  res.send('Home Page');
});

app.post('/submit', (req, res) => {
  res.send('Form submitted');
});
```

- `app.METHOD(PATH, HANDLER)`
    
- `METHOD`: HTTP method (`get`, `post`, etc.)
    
- `PATH`: route path (e.g., `/`, `/users`, `/products/:id`)
    

---

## 🧩 Route Parameters

Route parameters are named URL segments used to capture values.

```js
app.get('/users/:id', (req, res) => {
  const userId = req.params.id;
  res.send(`User ID: ${userId}`);
});
```

Multiple parameters:

```js
app.get('/posts/:postId/comments/:commentId', (req, res) => {
  const { postId, commentId } = req.params;
  res.send(`Post ${postId}, Comment ${commentId}`);
});
```

---

## 🔍 Query Parameters

Access query strings via `req.query`:

```js
app.get('/search', (req, res) => {
  const { q } = req.query;
  res.send(`You searched for: ${q}`);
});
```

Example URL: `/search?q=express`

---

## 🧱 Route Chaining (Same Path, Different Methods)

```js
app.route('/book')
  .get((req, res) => res.send('Get a book'))
  .post((req, res) => res.send('Add a book'))
  .put((req, res) => res.send('Update the book'));
```

---

## 🧩 Using Express Router

To organize routes better, use **Express Router** in separate modules.

### Create `routes/userRoutes.js`

```js
const express = require('express');
const router = express.Router();

router.get('/', (req, res) => {
  res.send('User list');
});

router.get('/:id', (req, res) => {
  res.send(`User ID: ${req.params.id}`);
});

module.exports = router;
```

### Use in `app.js`

```js
const userRoutes = require('./routes/userRoutes');
app.use('/users', userRoutes);
```

---

## ✅ Summary

- Define routes using `app.get`, `app.post`, etc.
    
- Use route and query parameters to make routes dynamic
    
- Organize large projects with `express.Router()`
    
- Use `app.route()` to chain handlers for the same route
    

---
