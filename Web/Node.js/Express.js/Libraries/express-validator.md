**`express-validator`** is a middleware for Express.js that helps validate and sanitize user input. It is built on top of [validator.js](https://github.com/validatorjs/validator.js) and integrates easily into Express route handlers.

---

## 📦 Installation

```bash
npm install express-validator
```

---

## 🧠 Key Concepts

- **Validation**: Checking if input data meets certain criteria (e.g., is an email, is not empty).
- **Sanitization**: Cleaning data (e.g., trimming whitespace, escaping HTML).
- **Middleware**: Express-validator works as middleware in your routes.

---

## 🛠 Basic Usage

```js
const { body, validationResult } = require('express-validator');

app.post('/register', [
  body('email').isEmail(),
  body('password').isLength({ min: 6 })
], (req, res) => {
  const errors = validationResult(req);
  if (!errors.isEmpty()) {
    return res.status(400).json({ errors: errors.array() });
  }

  // Proceed with creating the user
  res.send('User registered');
});
```

---

## ✨ Common Validators

```js
body('username').notEmpty()
body('email').isEmail()
body('age').isInt({ min: 0 })
body('password').isLength({ min: 8 })
body('website').optional().isURL()
```

---

## 🧼 Sanitization

```js
body('email').normalizeEmail()
body('username').trim().escape()
```

You can chain sanitizers with validators:
```js
body('username').trim().escape().notEmpty()
```

---

## 📦 Example: Full Route Validation

```js
const express = require('express');
const { body, validationResult } = require('express-validator');
const router = express.Router();

router.post('/users', [
  body('name').notEmpty().withMessage('Name is required'),
  body('email').isEmail().withMessage('Invalid email'),
  body('password').isLength({ min: 6 }).withMessage('Password must be at least 6 characters')
], (req, res) => {
  const errors = validationResult(req);
  if (!errors.isEmpty()) {
    return res.status(400).json({ errors: errors.array() });
  }
  // Continue with user creation
  res.status(201).json({ message: 'User created successfully' });
});

module.exports = router;
```

---

## 🧠 Accessing Validation Errors

```js
const errors = validationResult(req);
if (!errors.isEmpty()) {
  return res.status(400).json({ errors: errors.array() });
}
```

Each error object includes:
```js
{
  msg: 'Invalid email',
  param: 'email',
  location: 'body'
}
```

---

## ✅ Best Practices

- Validate **before** processing user input.
- Use `withMessage()` to provide custom error messages.
- Group validators in arrays for readability.
- Write reusable validation middlewares.

---

## 🔁 Reusable Middleware Example

**middleware/validators.js**
```js
const { body } = require('express-validator');

exports.userValidationRules = [
  body('email').isEmail().withMessage('Invalid email'),
  body('password').isLength({ min: 6 }).withMessage('Password too short')
];
```

**In route:**
```js
router.post('/login', userValidationRules, loginController);
```

---

## 📚 Summary

- `express-validator` is a powerful, flexible validation middleware for Express.
- Use it to ensure safe and valid input before using data.
- Integrate with route handlers and modularize validations.

> 💡 Validation is your first line of defense against malicious or malformed user input.
