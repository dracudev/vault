# Multer in Node.js

## Overview
**Multer** is a middleware for handling `multipart/form-data`, primarily used for uploading files in **Node.js** with **Express**.

It processes form-data and adds the files and form fields to the `req` object.

---

## Installing Multer
```bash
npm install multer
```

---

## Basic Example: Single File Upload
```javascript
const express = require('express');
const multer = require('multer');
const app = express();

// Configure Storage
const storage = multer.diskStorage({
  destination: function (req, file, cb) {
    cb(null, 'uploads/');
  },
  filename: function (req, file, cb) {
    cb(null, Date.now() + '-' + file.originalname);
  }
});

const upload = multer({ storage: storage });

// Single File Upload Endpoint
app.post('/upload', upload.single('myFile'), (req, res) => {
  console.log('File Info:', req.file);
  res.send('File uploaded successfully');
});

app.listen(3000, () => console.log('Server running on port 3000'));
```

---

## Multiple Files Upload
```javascript
// Upload up to 5 files
app.post('/uploads', upload.array('myFiles', 5), (req, res) => {
  console.log('Files Info:', req.files);
  res.send('Multiple files uploaded');
});
```

---

## Handling Form Data Along with Files
```javascript
app.post('/profile', upload.single('avatar'), (req, res) => {
  console.log('File:', req.file);
  console.log('Form Data:', req.body);
  res.send('Profile uploaded');
});
```

---

## File Filtering Example
```javascript
const fileFilter = (req, file, cb) => {
  if (file.mimetype === 'image/jpeg' || file.mimetype === 'image/png') {
    cb(null, true);
  } else {
    cb(new Error('Unsupported file type'), false);
  }
};

const uploadWithFilter = multer({ storage, fileFilter });

app.post('/upload-image', uploadWithFilter.single('image'), (req, res) => {
  res.send('Image uploaded');
});
```

---

## Storage Options
- **DiskStorage:** Stores files directly on disk.
- **MemoryStorage:** Stores files in memory as Buffer objects.

Example:
```javascript
const storage = multer.memoryStorage();
const upload = multer({ storage });
```

---

## Best Practices
- Always validate file types and sizes.
- Store sensitive files securely.
- Handle errors gracefully (e.g., invalid file type, size limit exceeded).

---

## Useful Resources
- [Multer GitHub Repository](https://github.com/expressjs/multer)
- [Official Multer Documentation](https://www.npmjs.com/package/multer)

---

## Summary
Multer simplifies file uploads in Node.js and Express applications, providing configurable storage, filtering, and error handling for robust file handling solutions.
