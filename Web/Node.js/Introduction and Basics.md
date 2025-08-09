## 📘 What is Node.js?

**Node.js** is a **runtime environment** that allows you to run JavaScript code **outside of a web browser**.

It uses **Google’s V8 JavaScript engine** (the same engine used in Chrome) to execute code on the **server-side**, making it possible to build full backend applications using JavaScript.

> 🚀 In short: Node.js lets you write server-side code in JavaScript.

---

## 🧠 Why Use Node.js?

- ✅ **Non-blocking I/O** – Efficient for handling multiple connections at once
    
- ✅ **Single programming language** – Use JavaScript for both frontend & backend
    
- ✅ **Vast ecosystem** – Thousands of packages available via `npm`
    
- ✅ **Fast and lightweight** – Thanks to the V8 engine and event-driven architecture
    
- ✅ **Scalable** – Ideal for microservices and APIs
    

---

## ⚙️ How Node.js Works

Node.js is **event-driven** and **asynchronous** by design.

- It uses an **event loop** to handle multiple operations **without blocking** the main thread.
    
- Common operations like file access, network requests, or database queries are handled asynchronously via **callbacks**, **promises**, or **async/await**.
    

> 🔀 The key idea: Node.js doesn't wait. While it performs I/O operations, it continues to serve other requests.

---

## 📦 Installing Node.js

You can install Node.js from the official site:

> 🔗 [https://nodejs.org/](https://nodejs.org/)

Use the LTS (Long Term Support) version for stability.

After installation, check versions:

```bash
node -v      # check Node.js version
npm -v       # check npm (Node Package Manager) version
```

---

## 📁 Node.js File Structure

A simple Node.js project might look like:

```
my-app/
├── index.js
├── package.json
├── package-lock.json
└── node_modules/
```

- `index.js`: your app's entry point
    
- `package.json`: metadata and dependencies
    
- `node_modules/`: installed packages
    

---

## 🛠️ Writing Your First Node.js Script

```js
// index.js
console.log("Hello from Node.js!");
```

Run it with:

```bash
node index.js
```

---

## 📚 Core Modules in Node.js

Node.js provides built-in modules without needing to install anything:

- `fs` – file system operations
    
- `http` – build HTTP servers
    
- `path` – work with file and directory paths
    
- `os` – get system information
    
- `events` – handle custom events
    

### Example: Using `fs` to read a file

```js
const fs = require('fs');

fs.readFile('example.txt', 'utf8', (err, data) => {
  if (err) {
    console.error("Error reading file:", err);
    return;
  }
  console.log("File contents:", data);
});
```

---

## 📦 What is npm?

**npm** (Node Package Manager) is the default package manager for Node.js.

- Install a package:
    
    ```bash
    npm install <package-name>
    ```
    
- Initialize a project:
    
    ```bash
    npm init -y
    ```
    
- Save a dev dependency:
    
    ```bash
    npm install --save-dev <package-name>
    ```
    

`package.json` keeps track of dependencies and scripts.

---

## ✅ Summary

- Node.js runs JavaScript outside the browser
    
- Uses event loop & asynchronous I/O for performance
    
- Built on the V8 engine (used in Chrome)
    
- Includes powerful built-in modules
    
- Uses `npm` to manage packages
    

---