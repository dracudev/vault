Controllers in Node.js are part of the **MVC (Model-View-Controller)** design pattern. They handle the **business logic** of your application and act as the intermediary between the Model (data) and the View (UI or client response).

In a typical Node.js + Express app, controllers are JavaScript files or modules where you define functions to handle HTTP requests (GET, POST, PUT, DELETE, etc).

---

## 🧠 Purpose of Controllers

- Organize your codebase by separating concerns.
- Abstract and encapsulate business logic.
- Handle requests and return appropriate responses.
- Call services or models to perform actions.

---

## 📁 Example Project Structure

```
project-root/
├── controllers/
│   └── userController.js
├── models/
│   └── userModel.js
├── routes/
│   └── userRoutes.js
├── app.js
```

---

## 📝 Example: Basic Controller

**controllers/userController.js**

```js
// Example controller for managing users

const getAllUsers = (req, res) => {
  res.status(200).json({ message: "Fetched all users" });
};

const getUserById = (req, res) => {
  const userId = req.params.id;
  res.status(200).json({ message: `Fetched user with ID: ${userId}` });
};

const createUser = (req, res) => {
  const newUser = req.body;
  res.status(201).json({ message: "User created", user: newUser });
};

module.exports = {
  getAllUsers,
  getUserById,
  createUser
};
```

---

## 📡 Hooking Controllers to Routes

**routes/userRoutes.js**

```js
const express = require('express');
const router = express.Router();
const userController = require('../controllers/userController');

router.get('/', userController.getAllUsers);
router.get('/:id', userController.getUserById);
router.post('/', userController.createUser);

module.exports = router;
```

---

## 🏁 Integration in Main App

**app.js**

```js
const express = require('express');
const app = express();
const userRoutes = require('./routes/userRoutes');

app.use(express.json());
app.use('/api/users', userRoutes);

app.listen(3000, () => {
  console.log('Server is running on port 3000');
});
```

---

## ✅ Best Practices

- Keep controllers focused on request handling.
- Delegate heavy logic to services or models.
- Always validate and sanitize incoming data.
- Return proper HTTP status codes and messages.
- Use async/await and try/catch for error handling.

---

## 🧪 Example with Async/Await & Error Handling

```js
const getUserById = async (req, res) => {
  try {
    const userId = req.params.id;
    const user = await User.findById(userId);
    if (!user) {
      return res.status(404).json({ error: 'User not found' });
    }
    res.status(200).json(user);
  } catch (error) {
    res.status(500).json({ error: 'Internal server error' });
  }
};
```

---

## 📚 Summary

- Controllers manage how HTTP requests are processed.
- They call models/services and return responses.
- Separate your logic into controllers for cleaner, maintainable code.

> 💡 Use a `controllers/` folder to keep all your route logic modular and organized.
