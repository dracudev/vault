## 📘 What is JSON?

**JSON** (JavaScript Object Notation) is a lightweight data-interchange format that’s easy for humans to read and write, and easy for machines to parse and generate.

It’s often used for:

- **API responses** (sending structured data)
    
- **Configuration files**
    
- **Data storage**
    
- **Documentation of APIs** (e.g., OpenAPI/Swagger specs in `.json`)
    

---

## 🛠 JSON Structure

A JSON document is made up of:

- **Objects** `{ ... }` → collections of key-value pairs
    
- **Arrays** `[ ... ]` → ordered lists of values
    
- **Values** → strings, numbers, booleans, null, objects, arrays
    

Example:

```json
{
  "name": "John Doe",
  "age": 30,
  "isAdmin": false,
  "skills": ["JavaScript", "Node.js", "React"],
  "address": {
    "city": "Madrid",
    "zip": "28001"
  }
}
```

---

## 📏 JSON Rules

1. Keys must be **strings** in double quotes (`"key"`).
    
2. Values can be:
    
    - String (`"Hello"`)
        
    - Number (`42`)
        
    - Boolean (`true` or `false`)
        
    - Null (`null`)
        
    - Object (`{}`)
        
    - Array (`[]`)
        
3. No trailing commas.
    
4. UTF-8 encoding is standard.
    

---

## 🔍 Reading and Writing JSON in Node.js

**Reading JSON:**

```js
const fs = require('fs');

const data = fs.readFileSync('data.json', 'utf8');
const obj = JSON.parse(data);
console.log(obj.name);
```

**Writing JSON:**

```js
const fs = require('fs');

const obj = { name: 'Alice', age: 25 };
fs.writeFileSync('data.json', JSON.stringify(obj, null, 2));
```

- `JSON.stringify(obj, null, 2)` formats JSON with 2-space indentation.
    

---

## 📜 JSON for API Documentation (jsonDocs)

When used as **API documentation**, JSON defines:

- **Endpoints** (`/users`, `/products`, etc.)
    
- **HTTP methods** (`GET`, `POST`, etc.)
    
- **Request parameters**
    
- **Response structure**
    

Example minimal API doc:

```json
{
  "openapi": "3.0.0",
  "info": {
    "title": "Sample API",
    "version": "1.0.0"
  },
  "paths": {
    "/users": {
      "get": {
        "summary": "Get all users",
        "responses": {
          "200": {
            "description": "List of users"
          }
        }
      }
    }
  }
}
```

---

## ✅ Best Practices for JSON Docs

- Use **camelCase** for keys.
    
- Keep it **consistent** (naming, indentation).
    
- Validate JSON with tools like [JSONLint](https://jsonlint.com/).
    
- For large APIs, split into **modular JSON files** and merge during build.
    

---

## 📚 Useful Tools

- **Online editors:** [JSON Editor Online](https://jsoneditoronline.org/)
    
- **Validators:** JSONLint, jq
    
- **Node.js helpers:** `JSON.parse()`, `JSON.stringify()`