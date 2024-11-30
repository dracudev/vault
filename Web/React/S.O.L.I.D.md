### **1. Single Responsibility Principle (SRP)**

**A class or component should have one, and only one, reason to change.**

- In React, each component should handle one specific part of the UI or logic.
```tsx
// BAD: A component doing both data fetching and rendering
function UserProfile() {
  const [user, setUser] = React.useState(null);

  React.useEffect(() => {
    fetch('/api/user')
      .then(response => response.json())
      .then(data => setUser(data));
  }, []);

  return user ? <div>{user.name}</div> : <p>Loading...</p>;
}

// GOOD: Separate data fetching and UI rendering
function UserProfile() {
  const user = useUser(); // Custom hook for fetching data
  return user ? <UserDetails user={user} /> : <p>Loading...</p>;
}

function UserDetails({ user }) {
  return <div>{user.name}</div>;
}

function useUser() {
  const [user, setUser] = React.useState(null);
  React.useEffect(() => {
    fetch('/api/user')
      .then(response => response.json())
      .then(data => setUser(data));
  }, []);
  return user;
}

```

### **2. Open/Closed Principle (OCP)**

**Software entities should be open for extension, but closed for modification.**

- In React, components should be designed to accommodate changes without modifying the existing code. Use props, context, or composition to achieve this.

```tsx 
// BAD: A hardcoded button component
function Button() {
  return <button style={{ backgroundColor: 'blue', color: 'white' }}>Click Me</button>;
}

// GOOD: A flexible button component
function Button({ style, children }) {
  return <button style={style}>{children}</button>;
}

// Extending without modifying
function App() {
  return (
    <Button style={{ backgroundColor: 'green', color: 'white' }}>Submit</Button>
  );
}

```


### **3. Liskov Substitution Principle (LSP)**

**Subtypes must be substitutable for their base types.**

- In React, components should respect their expected behavior when replaced by another with the same interface.

```tsx
// BAD: A specific header component that breaks the expected interface
function PageHeader({ title }) {
  return <h1>{title}</h1>;
}

// GOOD: A more generic header component
function PageHeader({ children }) {
  return <header>{children}</header>;
}

// Substituting a different implementation
function App() {
  return (
    <PageHeader>
      <h1>Main Title</h1>
      <p>Subtitle text</p>
    </PageHeader>
  );
}

```

### **4. Interface Segregation Principle (ISP)**

**Clients should not be forced to depend on methods they do not use.**

- In React, this means avoiding "fat" props or hooks. Components should receive only the data and callbacks they actually need.

```tsx
// BAD: A generic component receiving too many props
function UserCard({ name, age, address, email, phone }) {
  return (
    <div>
      <h1>{name}</h1>
      <p>{email}</p>
    </div>
  );
}

// GOOD: Split the responsibilities into smaller components
function UserCard({ name, email }) {
  return (
    <div>
      <h1>{name}</h1>
      <p>{email}</p>
    </div>
  );
}

```

### **5. Dependency Inversion Principle (DIP)**

**High-level modules should not depend on low-level modules. Both should depend on abstractions.**

- In React, this can be achieved by using dependency injection (e.g., passing dependencies via props, context, or hooks).

```tsx
// BAD: Hardcoded API call in a component
function UserProfile() {
  const [user, setUser] = React.useState(null);

  React.useEffect(() => {
    fetch('/api/user')
      .then(response => response.json())
      .then(data => setUser(data));
  }, []);

  return user ? <div>{user.name}</div> : <p>Loading...</p>;
}

// GOOD: Abstracted dependency
function UserProfile({ fetchUser }) {
  const [user, setUser] = React.useState(null);

  React.useEffect(() => {
    fetchUser().then(setUser);
  }, [fetchUser]);

  return user ? <div>{user.name}</div> : <p>Loading...</p>;
}

// Injecting the dependency
function App() {
  const fetchUser = () => fetch('/api/user').then(response => response.json());
  return <UserProfile fetchUser={fetchUser} />;
}

```