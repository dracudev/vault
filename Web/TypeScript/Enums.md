### Definition

- Enums represent a set of named constants, either numeric or string values.
- Useful for defining a fixed set of options.

### Key Features

1. Can be **numeric** (default) or **string-based**.
2. Automatically assigns incremental values for numeric enums.

### Syntax

Numeric Enums

```ts
enum Role {
  User,      // 0
  Admin,     // 1
  SuperAdmin // 2
}

const role: Role = Role.Admin;
console.log(role); // Outputs: 1
```

String Enums

```ts
enum Role {
  User = "USER",
  Admin = "ADMIN",
  SuperAdmin = "SUPERADMIN",
}

const role: Role = Role.User;
console.log(role); // Outputs: "USER"
```

### Usage

```ts
enum Status {
  Loading,
  Success,
  Error,
}

function handleStatus(status: Status) {
  if (status === Status.Loading) {
    console.log("Loading...");
  }
}
```

### **Computed and Constant Enums**

- **Computed**: Use expressions for values.
```ts
enum FileSize {
  KB = 1024,
  MB = KB * 1024,
  GB = MB * 1024,
}
```

**Constant**: Can be fully inlined at compile-time.
```ts
const enum Direction {
  Up,
  Down,
}

const move = Direction.Up; // No runtime object, just value 0
```