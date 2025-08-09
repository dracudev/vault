**Prisma** is a modern Node.js and TypeScript ORM that makes working with databases **type-safe**, **predictable**, and **developer-friendly**. It's especially popular for working with relational databases like PostgreSQL, MySQL, SQLite, SQL Server, and MongoDB.

---

## 🧠 Why Use Prisma?

- Auto-generated and type-safe query builder.
- Easy to setup and use.
- Clear data modeling using the `schema.prisma` file.
- Automatically generates client APIs.
- Integrates well with TypeScript.

---

## 📦 Installation

```bash
npm install prisma --save-dev
npm install @prisma/client
npx prisma init
```

This creates a `prisma/` folder with a `schema.prisma` file and a `.env` file.

---

## ⚙️ Example: Configuring Prisma

**.env**
```env
DATABASE_URL="postgresql://user:password@localhost:5432/mydb"
```

**prisma/schema.prisma**
```prisma
generator client {
  provider = "prisma-client-js"
}

datasource db {
  provider = "postgresql" // or mysql, sqlite, etc.
  url      = env("DATABASE_URL")
}

model User {
  id    Int     @id @default(autoincrement())
  name  String
  email String  @unique
  age   Int?
  posts Post[]
}

model Post {
  id      Int    @id @default(autoincrement())
  title   String
  content String?
  userId  Int
  user    User   @relation(fields: [userId], references: [id])
}
```

---

## 🔁 Migrate the Database

```bash
npx prisma migrate dev --name init
```

This will create SQL migrations and generate the Prisma Client.

---

## 📥 Using Prisma Client

**index.js**
```js
const { PrismaClient } = require('@prisma/client');
const prisma = new PrismaClient();

async function main() {
  const newUser = await prisma.user.create({
    data: {
      name: 'Alice',
      email: 'alice@example.com',
      age: 30,
    },
  });

  console.log('New user:', newUser);
}

main()
  .catch((e) => console.error(e))
  .finally(async () => await prisma.$disconnect());
```

---

## 🧪 Example CRUD Operations

```js
// Read all users
const users = await prisma.user.findMany();

// Update user
const updated = await prisma.user.update({
  where: { id: 1 },
  data: { age: 35 },
});

// Delete user
await prisma.user.delete({
  where: { id: 1 },
});
```

---

## 📡 Using in Express Controllers

```js
const { PrismaClient } = require('@prisma/client');
const prisma = new PrismaClient();

const getAllUsers = async (req, res) => {
  try {
    const users = await prisma.user.findMany();
    res.json(users);
  } catch (err) {
    res.status(500).json({ error: err.message });
  }
};
```

---

## ✅ Best Practices

- Use `.env` for environment variables.
- Regenerate Prisma Client after schema changes: `npx prisma generate`
- Handle errors and disconnection properly.
- Prefer `findUnique`, `findMany`, and `create` methods.

---

## 📚 Summary

- Prisma provides a clean, modern way to model and query your database.
- You define models in `schema.prisma` and Prisma generates a type-safe client.
- It supports migrations, relations, validations, and CRUD operations out of the box.

> 💡 Prisma is ideal for developers who want strict typing, great DX, and fast prototyping.
