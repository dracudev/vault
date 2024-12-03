## **1. Basic Prop Typing**

### **Required and Optional Props**
Use an interface or type alias to define the props' shape. Optional props are denoted with a `?`.

```tsx
interface BasicProps {
  name: string; // Required
  age?: number; // Optional
}

const Greeting: React.FC<BasicProps> = ({ name, age }) => {
  return (
    <div>
      <p>Hello, {name}!</p>
      {age && <p>Your age is {age}.</p>}
    </div>
  );
};

// Usage
<Greeting name="Alice" />;
<Greeting name="Bob" age={30} />;
```

### **Default Props**
Default values can be set for optional props to provide fallback behavior.

```tsx
interface Props {
  title?: string; // Optional
}

const Header: React.FC<Props> = ({ title = "Default Title" }) => {
  return <h1>{title}</h1>;
};

// Usage
<Header />; // Displays "Default Title"
<Header title="Custom Title" />; // Displays "Custom Title"
```

## **2. Props with Children**

When a component expects children, use `React.PropsWithChildren` to include them in the prop types.

```tsx
interface Props {
  message: string;
}

const Container: React.FC<React.PropsWithChildren<Props>> = ({ message, children }) => {
  return (
    <div>
      <h1>{message}</h1>
      <div>{children}</div>
    </div>
  );
};

// Usage
<Container message="Welcome">
  <p>This is a child component.</p>
</Container>;
```

## **3. Advanced Prop Typing**

### **Union Types**
Props can accept multiple types using union types.

```tsx
interface Props {
  status: "loading" | "success" | "error"; // Fixed values
}

const StatusIndicator: React.FC<Props> = ({ status }) => {
  if (status === "loading") return <p>Loading...</p>;
  if (status === "success") return <p>Success!</p>;
  if (status === "error") return <p>Error!</p>;
  return null;
};

// Usage
<StatusIndicator status="loading" />;
<StatusIndicator status="success" />;
```

### **Complex Props (Objects and Arrays)**
Define objects and arrays as props with detailed typing.

```tsx
interface Item {
  id: number;
  name: string;
}

interface ListProps {
  items: Item[]; // Array of objects
}

const ItemList: React.FC<ListProps> = ({ items }) => {
  return (
    <ul>
      {items.map((item) => (
        <li key={item.id}>{item.name}</li>
      ))}
    </ul>
  );
};

// Usage
<ItemList items={[{ id: 1, name: "Item 1" }, { id: 2, name: "Item 2" }]} />;
```

## **4. Utility Types for Props**

TypeScript provides utility types like `Partial`, `Required`, `Pick`, and `Omit` to manipulate prop types efficiently.

### **Partial**
Makes all props optional.

```tsx
interface Props {
  title: string;
  subtitle: string;
}

const Component: React.FC<Partial<Props>> = ({ title, subtitle }) => {
  return (
    <div>
      {title && <h1>{title}</h1>}
      {subtitle && <h2>{subtitle}</h2>}
    </div>
  );
};
```

### **Required**
Makes all props required, even if they were optional in the original type.

```tsx
const Component: React.FC<Required<Props>> = ({ title, subtitle }) => {
  return (
    <div>
      <h1>{title}</h1>
      <h2>{subtitle}</h2>
    </div>
  );
};
```

### **Pick and Omit**
Select or exclude specific properties from a type.

```tsx
interface Props {
  title: string;
  subtitle: string;
  description: string;
}

type TitleOnly = Pick<Props, "title">; // Only 'title'
type WithoutDescription = Omit<Props, "description">; // Excludes 'description'
```

## **5. Extending Prop Types**

Extend an existing type or interface to add additional properties.

```tsx
interface BaseProps {
  id: string;
}

interface ExtendedProps extends BaseProps {
  name: string;
}

const ExtendedComponent: React.FC<ExtendedProps> = ({ id, name }) => {
  return (
    <p>
      {id}: {name}
    </p>
  );
};

// Usage
<ExtendedComponent id="123" name="Alice" />;
```

## **6. Enums for Fixed Values**

Enums ensure only predefined values are passed to props.

```tsx
enum ButtonType {
  Primary = "primary",
  Secondary = "secondary",
}

interface ButtonProps {
  type: ButtonType;
}

const Button: React.FC<ButtonProps> = ({ type }) => {
  return <button className={type}>Click Me</button>;
};

// Usage
<Button type={ButtonType.Primary} />;
<Button type={ButtonType.Secondary} />;
```

## **7. Prop Validation with Generics**

Generics allow you to create reusable components with dynamic prop types.

```tsx
interface DropdownProps<T> {
  options: T[];
  onSelect: (option: T) => void;
}

const Dropdown = <T,>({ options, onSelect }: DropdownProps<T>) => {
  return (
    <select onChange={(e) => onSelect(options[+e.target.value])}>
      {options.map((option, index) => (
        <option key={index} value={index}>
          {String(option)}
        </option>
      ))}
    </select>
  );
};

// Usage
<Dropdown options={["Option 1", "Option 2"]} onSelect={(option) => alert(option)} />;
```