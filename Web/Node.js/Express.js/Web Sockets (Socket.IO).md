**WebSockets** allow for full-duplex communication between a client and server. In Node.js, the most popular library for working with WebSockets is **Socket.IO**, which simplifies real-time bidirectional event-based communication.

---

## 📦 Installation

```bash
npm install socket.io
```

If using with a client:
```bash
npm install socket.io-client
```

---

## 🧠 What is Socket.IO?

- Built on top of the WebSocket protocol.
- Provides fallbacks (long polling, etc.) for compatibility.
- Enables real-time features like chat, notifications, live data.

---

## ⚙️ Basic Server Setup

```js
const express = require('express');
const http = require('http');
const { Server } = require('socket.io');

const app = express();
const server = http.createServer(app);
const io = new Server(server);

io.on('connection', (socket) => {
  console.log('A user connected:', socket.id);

  socket.on('message', (msg) => {
    console.log('Received:', msg);
    io.emit('message', msg); // broadcast to all clients
  });

  socket.on('disconnect', () => {
    console.log('User disconnected:', socket.id);
  });
});

server.listen(3000, () => {
  console.log('Server running on http://localhost:3000');
});
```

---

## 🌐 Basic Client Setup

**HTML Example:**
```html
<!DOCTYPE html>
<html>
<head><title>Socket.IO Chat</title></head>
<body>
  <input id="input" />
  <ul id="messages"></ul>

  <script src="/socket.io/socket.io.js"></script>
  <script>
    const socket = io();

    socket.on('message', (msg) => {
      const li = document.createElement('li');
      li.textContent = msg;
      document.getElementById('messages').appendChild(li);
    });

    document.getElementById('input').addEventListener('keypress', function(e) {
      if (e.key === 'Enter') {
        socket.emit('message', this.value);
        this.value = '';
      }
    });
  </script>
</body>
</html>
```

---

## 📡 Namespaces & Rooms

### Namespaces
Allow splitting communication channels.
```js
const adminNamespace = io.of('/admin');
adminNamespace.on('connection', (socket) => {
  console.log('Admin connected:', socket.id);
});
```

### Rooms
Clients can join rooms to receive group messages.
```js
socket.join('room1');
io.to('room1').emit('message', 'Hello room1');
```

---

## 🔐 Middleware for Authentication

```js
io.use((socket, next) => {
  const token = socket.handshake.auth.token;
  if (isValidToken(token)) {
    return next();
  }
  return next(new Error('Authentication error'));
});
```

---

## 🧪 Testing with Postman or Web Clients

Socket.IO connections cannot be tested with regular HTTP tools. Use:
- **Browser dev tools**
- **Socket.IO client**
- **WebSocket GUI tools** like [wscat](https://github.com/websockets/wscat)

---

## ✅ Best Practices

- Use namespaces/rooms for scalable structure.
- Clean up on disconnect.
- Validate data sent by clients.
- Handle reconnections properly.
- Use authentication middleware.

---

## 📚 Summary

- WebSockets allow real-time communication between server and clients.
- Socket.IO simplifies setup, supports fallback transports, and offers useful abstractions like rooms and namespaces.
- Ideal for building chats, live dashboards, multiplayer games, etc.

> 💡 Socket.IO is event-driven: clients and servers exchange named events with optional data.
