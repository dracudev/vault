**`express-session`** is a middleware for Express.js that enables **server-side session management**. Sessions are used to store user data between HTTP requests, such as login states, cart information, or preferences.

---

## 📦 Installation

```bash
npm install express-session
```

---

## ⚙️ Basic Usage

```js
const express = require('express');
const session = require('express-session');

const app = express();

app.use(session({
  secret: 'mySecretKey',
  resave: false,
  saveUninitialized: false,
  cookie: {
    maxAge: 1000 * 60 * 60, // 1 hour
  },
}));

app.get('/', (req, res) => {
  if (req.session.views) {
    req.session.views++;
    res.send(`Views: ${req.session.views}`);
  } else {
    req.session.views = 1;
    res.send('Welcome! Refresh to track views.');
  }
});
```

---

## 🧠 Key Options

| Option             | Description |
|--------------------|-------------|
| `secret`           | Used to sign the session ID cookie. Keep it secret! |
| `resave`           | Forces session to be saved even if unmodified. Usually `false`. |
| `saveUninitialized`| Saves uninitialized sessions (no data). Set to `false` for login-only sessions. |
| `cookie`           | Configures the cookie (e.g., `maxAge`, `secure`, `httpOnly`) |

---

## 🔐 Storing Auth Data

```js
app.post('/login', (req, res) => {
  // After authentication
  req.session.user = { id: 123, name: 'Alice' };
  res.send('Logged in');
});

app.get('/profile', (req, res) => {
  if (req.session.user) {
    res.send(`Hello, ${req.session.user.name}`);
  } else {
    res.status(401).send('Unauthorized');
  }
});
```

---

## 🗑 Destroying a Session

```js
app.post('/logout', (req, res) => {
  req.session.destroy(err => {
    if (err) return res.status(500).send('Logout failed');
    res.clearCookie('connect.sid');
    res.send('Logged out');
  });
});
```

---

## 🛠 Session Stores

By default, session data is stored in memory (not for production). Use a store like:

- `connect-mongo` (MongoDB)
- `connect-redis` (Redis)
- `express-mysql-session` (MySQL)

### Example with MongoDB (connect-mongo):
```bash
npm install connect-mongo
```

```js
const MongoStore = require('connect-mongo');

app.use(session({
  secret: 'mySecretKey',
  store: MongoStore.create({ mongoUrl: 'mongodb://localhost/myapp' }),
  resave: false,
  saveUninitialized: false
}));
```

---

## 🔒 Best Practices

- Use a strong, secure `secret`.
- Set `secure: true` in cookies for HTTPS.
- Use a session store in production.
- Always clear session cookies on logout.
- Keep session data minimal (e.g., user ID only).

---

## 📚 Summary

- `express-session` enables session handling in Express apps.
- Store user data server-side for features like authentication.
- For production, use a dedicated session store.

> 💡 Sessions persist across HTTP requests and help manage user states securely.
