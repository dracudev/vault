## 📘 What is Swagger?

**Swagger** (now part of the **OpenAPI Specification**) is a toolset that helps you:

- Design APIs
    
- Document endpoints
    
- Provide interactive API testing via a web UI
    

With Swagger, you can create an API spec in **YAML/JSON** format and serve a user-friendly documentation page.

---

## 📦 Installing Swagger in Express.js

You’ll need two main packages:

```bash
npm install swagger-ui-express swagger-jsdoc
```

- **swagger-ui-express** → Serves the Swagger UI in your app
    
- **swagger-jsdoc** → Generates Swagger/OpenAPI docs from JSDoc comments
    

---

## 🛠️ Basic Setup

```js
const express = require('express');
const swaggerUi = require('swagger-ui-express');
const swaggerJsdoc = require('swagger-jsdoc');

const app = express();

// Swagger definition
const swaggerOptions = {
  definition: {
    openapi: '3.0.0',
    info: {
      title: 'My API',
      version: '1.0.0',
      description: 'API Documentation',
    },
    servers: [
      {
        url: 'http://localhost:3000',
      },
    ],
  },
  apis: ['./routes/*.js'], // Path to your API routes
};

const swaggerDocs = swaggerJsdoc(swaggerOptions);
app.use('/api-docs', swaggerUi.serve, swaggerUi.setup(swaggerDocs));

app.listen(3000, () => console.log('Server running on port 3000'));
```

Now, visiting **`http://localhost:3000/api-docs`** will show your Swagger UI.

---

## ✏️ Adding JSDoc Comments to Routes

In your route files (e.g., `routes/user.js`):

```js
/**
 * @swagger
 * /users:
 *   get:
 *     summary: Get all users
 *     responses:
 *       200:
 *         description: List of users
 */
app.get('/users', (req, res) => {
  res.json([{ id: 1, name: 'John Doe' }]);
});
```

Run your server again, and Swagger UI will show this endpoint.

---

## 📂 Folder Structure Example

```
project/
│   app.js
│   package.json
├── routes/
│   └── user.js
└── docs/
    └── swagger.js (optional config file)
```
