## 📘 What is Middleware?

**Middleware** in Express.js are functions that execute **during the lifecycle of a request**. They have access to:

- `req` (request object)
    
- `res` (response object)
    
- `next()` (a function to move to the next middleware)
    

### 📐 Middleware Signature:

```js
function (req, res, next) {
  // logic here
  next();
}
```

---

## 🔁 Types of Middleware

1. **Application-level middleware**
    
2. **Router-level middleware**
    
3. **Built-in middleware**
    
4. **Third-party middleware**
    
5. **Error-handling middleware**
    

---

## ⚙️ Application-Level Middleware

Applied globally to the `app` instance.

```js
app.use((req, res, next) => {
  console.log(`${req.method} ${req.url}`);
  next();
});
```

Only for specific routes:

```js
app.use('/api', (req, res, next) => {
  console.log('API middleware');
  next();
});
```

---

## 🧭 Router-Level Middleware

Attach middleware to `express.Router()` instances.

```js
const router = express.Router();

router.use((req, res, next) => {
  console.log('Router middleware');
  next();
});

router.get('/', (req, res) => {
  res.send('Hello from router');
});
```

---

## 🔧 Built-In Middleware

Express has some built-in middleware:

```js
app.use(express.static('public')); // serve static files
app.use(express.json());           // parse JSON bodies
app.use(express.urlencoded({ extended: true })); // parse form data
```

---

## 📦 Third-Party Middleware

Install and use packages like:

- `morgan` – logging
    
- `cors` – enable CORS
    
- `helmet` – security headers
    

### Example: Using `morgan`

```bash
npm install morgan
```

```js
const morgan = require('morgan');
app.use(morgan('dev'));
```

---

## ❗ Error-Handling Middleware

These middleware have **4 parameters**:

```js
app.use((err, req, res, next) => {
  console.error(err.stack);
  res.status(500).send('Something broke!');
});
```

Must be added **after all other middleware and routes**.

---

## 📌 Order of Middleware Matters

Middleware is executed **in the order it is declared**. For example:

```js
app.use(middleware1);
app.use(middleware2);
app.get('/', handler);
```

If `middleware1` doesn’t call `next()`, the request will not proceed.

---

## ✅ Summary

- Middleware functions can inspect, modify, or short-circuit requests
    
- Use them globally (`app.use`) or locally (`router.use`)
    
- Use third-party packages like `morgan`, `cors`, `helmet`
    
- Error-handling middleware must have 4 parameters and go at the end
    

---