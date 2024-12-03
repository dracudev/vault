| **Feature**       | **Interface**                   | **Type Alias**                             |
| ----------------- | ------------------------------- | ------------------------------------------ |
| **Merging**       | Can merge declarations          | Cannot merge declarations                  |
| **Flexibility**   | Only for object-like structures | Supports any type (union, primitive, etc.) |
| **Extensibility** | Extendable with `extends`       | Extendable with intersections              |
| **Performance**   | Slightly better performance     | Slightly slower for complex types          |

## **1. Interfaces**

### Definition
- Defines the structure (shape) of an object, specifying required and optional properties.
- Primarily used for defining object types.

### Key Features
1. **Optional Properties**: Use `?` to make properties optional.
2. **Read-Only Properties**: Use `readonly` to make properties immutable.
3. **Index Signatures**: Define properties with dynamic keys.

### Syntax

```ts
interface User {
  id: number;
  name: string;
  isAdmin?: boolean; // Optional property
  readonly createdAt: Date; // Read-only property
}
```

### Usage

```ts
const user: User = {
  id: 1,
  name: "Alice",
  createdAt: new Date(),
};
```

### Extending Interfaces

- Use `extends` to build upon existing interfaces.

```ts
interface Base {
  id: number;
}

interface Admin extends Base {
  permissions: string[];
}

const admin: Admin = { id: 1, permissions: ["read", "write"] };
```

### Merging Interfaces

- Interfaces with the same name automatically merge.

```ts
interface User {
  age: number;
}

interface User {
  name: string;
}

// Result:
const person: User = { age: 30, name: "John" };
```

## **2. Type Aliases**

### Definition

- A way to define custom types, including objects, primitives, unions, tuples, etc.
- More flexible than interfaces.

### Key Features

1. Cannot merge like interfaces.
2. Can represent more than just objects (e.g., unions, intersections, primitives).

### Syntax

```ts
type User = {
  id: number;
  name: string;
  isAdmin?: boolean;
};

type UserId = string | number; // Union type
```

### Usage

```ts
const user: User = { id: 1, name: "Alice" };
const id: UserId = 123; // Can be string or number
```

### Union and Intersection with Types

- **Union**: Combine multiple types as an OR condition.
```ts
type Result = "success" | "error";

const status: Result = "success"; // Only "success" or "error" allowed
```

- **Intersection**: Combine multiple types as an AND condition.
```ts
type Base = { id: number };
type Admin = { permissions: string[] };

type AdminUser = Base & Admin;

const admin: AdminUser = { id: 1, permissions: ["read", "write"] };
```

