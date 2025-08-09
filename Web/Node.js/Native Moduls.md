Node.js includes several built-in modules that provide essential functionality without requiring external dependencies. These native modules are part of the Node.js runtime and can be imported using the `require()` function.

---

## Importing Native Modules

```js
const fs = require('fs');
const http = require('http');
```

Or using ES Modules:

```js
import fs from 'fs';
import http from 'http';
```

---

## Common Native Modules

### 1. **fs (File System)**

Provides functions to interact with the file system.

- **Read File**
    

```js
fs.readFile('example.txt', 'utf8', (err, data) => {
  if (err) throw err;
  console.log(data);
});
```

- **Write File**
    

```js
fs.writeFile('example.txt', 'Hello, Node.js!', err => {
  if (err) throw err;
  console.log('File written successfully');
});
```

- **Sync Versions**: `readFileSync`, `writeFileSync`
    

---

### 2. **http**

Used to create web servers and handle HTTP requests and responses.

```js
const server = http.createServer((req, res) => {
  res.writeHead(200, { 'Content-Type': 'text/plain' });
  res.end('Hello, World!');
});

server.listen(3000, () => {
  console.log('Server is running on http://localhost:3000');
});
```

---

### 3. **path**

Utilities for handling and transforming file paths.

```js
const path = require('path');

const fullPath = path.join(__dirname, 'folder', 'file.txt');
console.log(fullPath);
```

- `path.basename()`, `path.extname()`, `path.resolve()`
    

---

### 4. **os**

Provides information about the operating system.

```js
const os = require('os');

console.log(os.platform());
console.log(os.totalmem());
```

---

### 5. **events**

Enables the creation and handling of custom events.

```js
const EventEmitter = require('events');
const emitter = new EventEmitter();

emitter.on('greet', () => {
  console.log('Hello from event!');
});

emitter.emit('greet');
```

---

### 6. **crypto**

Used for cryptographic operations.

```js
const crypto = require('crypto');

const hash = crypto.createHash('sha256').update('password').digest('hex');
console.log(hash);
```

---

### 7. **url**

Provides utilities for URL resolution and parsing.

```js
const url = require('url');

const myUrl = new URL('https://example.com/path?name=John');
console.log(myUrl.hostname); // 'example.com'
console.log(myUrl.searchParams.get('name')); // 'John'
```

---

### 8. **util**

Various utility functions.

- `util.promisify()` turns callback-based functions into promise-based ones.
    

```js
const util = require('util');
const readFile = util.promisify(fs.readFile);

readFile('example.txt', 'utf8')
  .then(data => console.log(data))
  .catch(err => console.error(err));
```

---
