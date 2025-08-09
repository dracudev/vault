## Overview
JWT (JSON Web Token) is a compact, URL-safe means of representing claims to be transferred between two parties. It's commonly used for **authentication** and **information exchange**.

- **Structure of a JWT:**
  - Header
  - Payload
  - Signature

Example token:
```
xxxxx.yyyyy.zzzzz
```

---

## Why Use JWT?
- **Stateless Authentication:** No need to store sessions server-side.
- **Compact:** Easily sent via URL, POST parameters, or HTTP header.
- **Self-contained:** Includes all required information.

---

## Installing Dependencies
```bash
npm install jsonwebtoken dotenv
```

---

## Example Usage

### 1. Creating a JWT
```javascript
const jwt = require('jsonwebtoken');
require('dotenv').config();

const user = { id: 1, username: 'john_doe' };
const secretKey = process.env.JWT_SECRET || 'your-secret-key';

const token = jwt.sign(user, secretKey, { expiresIn: '1h' });
console.log('Generated Token:', token);
```

### 2. Verifying a JWT
```javascript
jwt.verify(token, secretKey, (err, decoded) => {
  if (err) {
    console.error('Token verification failed:', err);
  } else {
    console.log('Decoded Token Data:', decoded);
  }
});
```

### 3. Middleware for Express Authentication
```javascript
const express = require('express');
const app = express();

function authenticateToken(req, res, next) {
  const authHeader = req.headers['authorization'];
  const token = authHeader && authHeader.split(' ')[1];

  if (!token) return res.sendStatus(401);

  jwt.verify(token, secretKey, (err, user) => {
    if (err) return res.sendStatus(403);
    req.user = user;
    next();
  });
}

app.get('/protected', authenticateToken, (req, res) => {
  res.json({ message: 'Protected content', user: req.user });
});

app.listen(3000, () => console.log('Server running on port 3000'));
```

---

## JWT Best Practices
- Always use **HTTPS** to prevent token interception.
- Store JWT securely (e.g., HttpOnly cookies or Secure storage on client).
- Set appropriate expiration (`expiresIn`).
- Use strong, random secret keys.
- Optionally implement **token blacklisting** or **refresh tokens** for added security.

---

## Useful Resources
- [JWT.io Debugger](https://jwt.io/)
- [jsonwebtoken NPM Package](https://www.npmjs.com/package/jsonwebtoken)

---

## Summary
JWT provides a lightweight and efficient way to handle authentication in Node.js applications, especially when designing **RESTful APIs** or **microservices**.
