### Summary Table

|Hook|Purpose|Common Use Cases|
|---|---|---|
|`useEffect`|Perform side effects in functional components|Data fetching, subscriptions, DOM updates|
|`useState`|Manage local state in functional components|Form inputs, toggles, counters|
|`useContext`|Access shared data from a React context|Theme, authentication, global state management|

---

## 1. `useEffect`
### Explanation:
`useEffect` is a React Hook that lets you perform side effects in functional components. It runs after the component renders and can be used to handle actions like data fetching, subscriptions, or DOM manipulations.  
### Syntax: 
```jsx
useEffect(() => {   // Your side effect logic here }, [dependencies]);
```

### Key Points:

- **No dependencies (`[]`)**: The effect runs only once after the initial render.
- **With dependencies**: The effect runs only when the specified dependencies change.
- **Without dependency array**: The effect runs after every render.
- Cleanup can be performed by returning a function from the effect.

### Common Use Cases:

1. **Fetching data from an API**
2. **Setting up subscriptions (e.g., WebSocket)**
3. **Updating the DOM (e.g., document title)**

### Example:

```jsx 
import React, { useEffect, useState } from 'react';

function FetchDataComponent() {
  const [data, setData] = useState([]);

  useEffect(() => {
    fetch('https://api.example.com/data')
      .then(response => response.json())
      .then(json => setData(json));

    // Cleanup example (optional)
    return () => {
      console.log('Cleanup logic here');
    };
  }, []); // Runs only once after the first render

  return (
    <div>
      <h1>Fetched Data</h1>
      <ul>
        {data.map(item => (
          <li key={item.id}>{item.name}</li>
        ))}
      </ul>
    </div>
  );
}
```

---
## 2. `useState`

### Explanation:

`useState` is a Hook that lets you add state management to functional components. It provides a state variable and a function to update that state.

### Syntax:

```jsx
const [state, setState] = useState(initialValue);
```

### Key Points:

- `useState` takes an initial value for the state.
- The state update function can accept either a new value or a function to compute the next state.
- Updating state triggers a re-render of the component.

### Common Use Cases:

1. **Managing form inputs**
2. **Toggling UI components (e.g., modals, dropdowns)**
3. **Tracking counters or other dynamic values**

### Example:

```jsx
import React, { useState } from 'react';

function Counter() {
  const [count, setCount] = useState(0);

  const increment = () => setCount(count + 1);
  const decrement = () => setCount(count - 1);

  return (
    <div>
      <h1>Counter: {count}</h1>
      <button onClick={increment}>Increment</button>
      <button onClick={decrement}>Decrement</button>
    </div>
  );
}
```

---
## 3. `useContext`

### Explanation:

`useContext` is a React Hook that allows functional components to access data from a React context directly without using `Context.Consumer`.

### Syntax:

```jsx
const value = useContext(Context);
```

### Key Points:

- Context provides a way to pass data through the component tree without manually passing props.
- `useContext` must be used with a context created by `React.createContext`.
- It's useful for global state management like themes, authentication, etc.

### Common Use Cases:

1. **Theme management (light/dark mode)**
2. **User authentication**
3. **Sharing data across deeply nested components**

### Example:

```jsx
import React, { useContext, createContext, useState } from 'react';

// Create a Context
const ThemeContext = createContext();

function App() {
  const [theme, setTheme] = useState('light');

  return (
    <ThemeContext.Provider value={{ theme, setTheme }}>
      <ThemedComponent />
    </ThemeContext.Provider>
  );
}

function ThemedComponent() {
  const { theme, setTheme } = useContext(ThemeContext);

  const toggleTheme = () => {
    setTheme(theme === 'light' ? 'dark' : 'light');
  };

  return (
    <div style={{ background: theme === 'light' ? '#fff' : '#333', color: theme === 'light' ? '#000' : '#fff' }}>
      <h1>Current Theme: {theme}</h1>
      <button onClick={toggleTheme}>Toggle Theme</button>
    </div>
  );
}

export default App;
```

---

