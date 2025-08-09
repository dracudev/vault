**`cookie-session`** is a lightweight session middleware that stores session data entirely in a **cookie** (client-side), rather than on the server. This is useful for small apps or where session storage needs to be stateless.

---

## 📦 Installation

```bash
npm install cookie-session
```

---

## ⚙️ Basic Usage

```js
const express = require('express');
const cookieSession = require('cookie-session');

const app = express();

app.use(cookieSession({
  name: 'session',
  keys: ['mySecretKey1', 'mySecretKey2'],

  // Cookie Options
  maxAge: 24 * 60 * 60 * 1000 // 24 hours
}));

app.get('/', (req, res) => {
  req.session.views = (req.session.views || 0) + 1;
  res.send(`Viewed ${req.session.views} times`);
});
```

---

## 🧠 Key Options

| Option      | Description |
|-------------|-------------|
| `name`      | Cookie name (defaults to `session`) |
| `keys`      | Array of keys for signing cookies |
| `maxAge`    | Expiry time in milliseconds |
| `secure`    | Send cookie over HTTPS only |
| `httpOnly`  | Restrict cookie from client-side scripts |

---

## 🔐 Storing Auth Data in Session

```js
app.post('/login', (req, res) => {
  req.session.user = { id: 123, name: 'Alice' };
  res.send('Logged in');
});

app.get('/profile', (req, res) => {
  if (req.session.user) {
    res.send(`Hello ${req.session.user.name}`);
  } else {
    res.status(401).send('Unauthorized');
  }
});
```

---

## 🗑 Destroying a Session

```js
app.post('/logout', (req, res) => {
  req.session = null;
  res.send('Logged out');
});
```

---

## ✅ Use Cases

- Lightweight apps that don’t require storing sessions in a database.
- Stateless APIs with short-lived sessions.
- Apps that need fast, simple session handling without external stores.

---

## ⚠️ Limitations

- Session data is stored in the cookie, so:
  - Must be small (under 4KB total)
  - Not suitable for sensitive or large data
  - Easily visible to the client (although signed)

---

## 🔒 Best Practices

- Always set `httpOnly` and `secure` flags.
- Rotate keys periodically for added security.
- Never store passwords or secrets in session.
- Validate session data on each request.

---

## 📚 Summary

- `cookie-session` stores session data client-side using cookies.
- It's simple and stateless—great for small to medium apps.
- Prefer `express-session` with a store for large or sensitive data.

> 💡 Keep sessions lightweight and secure when using `cookie-session`.
