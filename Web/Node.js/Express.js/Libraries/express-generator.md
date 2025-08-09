**`express-generator`** is a command-line tool that scaffolds a basic Express.js application structure. It helps you get up and running quickly by generating a boilerplate app with pre-configured views, routes, middleware, and static files.

---

## 📦 Installation

Install globally:
```bash
npm install -g express-generator
```

---

## 🚀 Create a New Express App

```bash
express myapp
```

Options:
```bash
express --view=pug myapp       # Use Pug as the template engine (default)
express --view=ejs myapp       # Use EJS
express --no-view myapp        # No template engine
express --git                  # Create a .gitignore file
express --force                # Force on non-empty directory
```

Example:
```bash
express --view=ejs myapp
cd myapp
npm install
npm start
```

---

## 📁 Generated Project Structure

```
myapp/
├── app.js
├── package.json
├── /bin
│   └── www
├── /public
│   ├── images/
│   ├── javascripts/
│   └── stylesheets/
│       └── style.css
├── /routes
│   ├── index.js
│   └── users.js
├── /views
│   ├── error.ejs
│   ├── index.ejs
│   └── layout.ejs
```

---

## ⚙️ Key Files

### `app.js`
- Main application file
- Sets up middleware, routes, views, and error handling

### `bin/www`
- Starts the server (calls `app.listen`)

### `routes/`
- Contains route modules (e.g. `/`, `/users`)

### `views/`
- Contains view templates (EJS, Pug, etc.)

---

## 🧪 Running the App

```bash
npm start
```

Visit: `http://localhost:3000`

---

## 🎨 Choosing a View Engine

Supported engines:
- Pug (default)
- EJS
- HBS
- Mustache

If using `--no-view`, you can build an API-only project.

---

## ✅ Best Practices After Generating

- Replace placeholder code with your actual logic.
- Organize your routes and controllers in a modular way.
- Add `.env` config using dotenv.
- Use a linter (e.g., ESLint) and formatter (e.g., Prettier).
- Add testing framework like Jest or Mocha.

---

## 📚 Summary

- `express-generator` scaffolds a ready-to-run Express app.
- Helps speed up development by providing structure and boilerplate.
- Ideal for quickly starting new projects or learning Express basics.

> 💡 Use `express-generator` for rapid prototyping or to kickstart a structured Express.js project.
