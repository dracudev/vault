Models in Node.js represent the **data layer** of your application. When working with relational databases like **PostgreSQL**, **MySQL**, or **SQLite**, Sequelize is a popular **ORM (Object-Relational Mapping)** library that allows you to define models and interact with your database using JavaScript.

---

## 🧠 Purpose of Models

- Define the **structure** of tables in the database.
- Interact with the database using high-level JavaScript APIs.
- Perform **CRUD** operations easily.
- Represent relationships between tables.

---

## 📦 Installing Sequelize

You need to install both `sequelize` and a database driver (e.g. for PostgreSQL):

```bash
npm install sequelize pg pg-hstore
```

Or for MySQL:

```bash
npm install sequelize mysql2
```

---

## ⚙️ Sequelize Initialization Example

**db.js** (database connection setup)

```js
const { Sequelize } = require('sequelize');

const sequelize = new Sequelize('database_name', 'username', 'password', {
  host: 'localhost',
  dialect: 'postgres', // or 'mysql', 'sqlite', etc.
});

module.exports = sequelize;
```

---

## 📝 Example: Defining a User Model

**models/user.js**

```js
const { DataTypes } = require('sequelize');
const sequelize = require('../db');

const User = sequelize.define('User', {
  name: {
    type: DataTypes.STRING,
    allowNull: false
  },
  email: {
    type: DataTypes.STRING,
    allowNull: false,
    unique: true,
    validate: {
      isEmail: true
    }
  },
  age: {
    type: DataTypes.INTEGER,
    defaultValue: 0
  }
}, {
  timestamps: true,
});

module.exports = User;
```

---

## 🔁 Syncing the Model

```js
const sequelize = require('./db');
const User = require('./models/user');

sequelize.sync({ force: false })
  .then(() => console.log("Database synced"))
  .catch(err => console.error("Sync failed:", err));
```

---

## 📡 Using the Model in Controllers

```js
const User = require('../models/user');

const getAllUsers = async (req, res) => {
  try {
    const users = await User.findAll();
    res.json(users);
  } catch (err) {
    res.status(500).json({ error: err.message });
  }
};
```

---

## 🔗 Relationships Between Models

```js
User.hasMany(Post);
Post.belongsTo(User);
```

---

## ✅ Best Practices

- Keep models simple and focused.
- Use Sequelize validations for input checking.
- Handle associations in a separate file or initialization script.
- Use environment variables for DB credentials.

---

## 🧪 Testing the Model

```js
const User = require('./models/user');

(async () => {
  const newUser = await User.create({ name: 'Alice', email: 'alice@example.com', age: 30 });
  console.log('New User:', newUser.toJSON());
})();
```

---

## 📚 Summary

- Sequelize helps manage SQL databases with models in Node.js.
- Define models using `sequelize.define()`.
- Perform CRUD operations and define relationships.
- Use validations, default values, and hooks to enrich your models.

> 💡 Keep your `models/` directory clean and use one file per model.
