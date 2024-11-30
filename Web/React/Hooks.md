### Summary Table
| Hook         | Purpose                                       | Common Use Cases                               |
| ------------ | --------------------------------------------- | ---------------------------------------------- |
| `useEffect`  | Perform side effects in functional components | Data fetching, subscriptions, DOM updates      |
| `useState`   | Manage local state in functional components   | Form inputs, toggles, counters                 |
| `useContext` | Access shared data from a React context       | Theme, authentication, global state management |
| `useRef`     | Create a mutable reference that persists      | Accessing DOM elements, storing timers, persisting mutable values |
| `useMemo`    | Memoize a computed value                      | Optimizing expensive calculations, avoiding unnecessary re-renders |
| `useReducer` | Manage complex state transitions              | Centralizing state logic, managing complex state with sub-values |
| `useCallback`| Memoize a function to prevent re-creation      | Passing stable callbacks to children, optimizing event handlers |

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

## 4. `useRef`

### Explanation:

`useRef` is a React Hook that allows you to create a mutable reference that persists across renders. It can store a reference to a DOM element or any mutable value without triggering a re-render when updated.

### Syntax:

```jsx
const ref = useRef(initialValue);
```

### Key Points:

- **Mutable Object**: The `useRef` hook returns an object with a `.current` property that can be updated directly.
- **No Re-rendering**: Changing the `.current` property does not cause a re-render of the component.
- **Accessing DOM Nodes**: Commonly used to reference DOM elements for direct manipulation.
- **Persisting Values**: Can store values that need to persist across renders but don’t need to trigger a re-render when changed.

### Common Use Cases:

1. **Accessing and manipulating DOM elements (e.g., focusing an input)**
2. **Storing mutable values across renders (e.g., timers, counters)**
3. **Tracking previous values without re-renders**

### Example:

#### Accessing DOM Elements:

```jsx
import React, { useRef } from 'react';

function FocusInput() {
  const inputRef = useRef(null);

  const handleFocus = () => {
    inputRef.current.focus(); // Directly accessing the DOM node
  };

  return (
    <div>
      <input ref={inputRef} type="text" placeholder="Type something" />
      <button onClick={handleFocus}>Focus Input</button>
    </div>
  );
}

export default FocusInput;
```

Persisting Values:
```jsx
import React, { useRef, useState } from 'react';

function Timer() {
  const [count, setCount] = useState(0);
  const timerRef = useRef(null);

  const startTimer = () => {
    if (!timerRef.current) {
      timerRef.current = setInterval(() => setCount(c => c + 1), 1000);
    }
  };

  const stopTimer = () => {
    clearInterval(timerRef.current);
    timerRef.current = null;
  };

  return (
    <div>
      <h1>Timer: {count}s</h1>
      <button onClick={startTimer}>Start</button>
      <button onClick={stopTimer}>Stop</button>
    </div>
  );
}

export default Timer;
```

---

## 5. `useMemo`

### Explanation:

`useMemo` is a React Hook that memoizes a computed value to optimize performance. It recalculates the value only when one of its dependencies changes, avoiding unnecessary computations during re-renders.

### Syntax:

```jsx
const memoizedValue = useMemo(() => computeExpensiveValue(dependencies), [dependencies]);
```

### Key Points:

- **Performance Optimization**: Use for expensive calculations that don’t need to run on every render.
- **Dependency Array**: The memoized value is recomputed only when one of the dependencies changes.
- **Avoid Overuse**: Use it only when performance issues arise from unnecessary re-computation.

### Common Use Cases:

1. **Optimizing expensive calculations**
2. **Avoiding unnecessary re-renders when passing props to child components**
3. **Deriving state values from complex logic**

### Example:

#### Optimizing Expensive Calculations:

```jsx
import React, { useState, useMemo } from 'react';

function ExpensiveCalculation({ num }) {
  const computeFactorial = n => {
    console.log('Calculating factorial...');
    return n <= 1 ? 1 : n * computeFactorial(n - 1);
  };

  const factorial = useMemo(() => computeFactorial(num), [num]);

  return <div>Factorial of {num}: {factorial}</div>;
}

function App() {
  const [num, setNum] = useState(1);

  return (
    <div>
      <input
        type="number"
        value={num}
        onChange={e => setNum(parseInt(e.target.value) || 0)}
      />
      <ExpensiveCalculation num={num} />
    </div>
  );
}

export default App;
```

Avoiding Unnecessary Re-renders:
```jsx
import React, { useState, useMemo } from 'react';

function Child({ items }) {
  console.log('Child component rendered!');
  return <ul>{items.map(item => <li key={item}>{item}</li>)}</ul>;
}

function App() {
  const [count, setCount] = useState(0);
  const [filter, setFilter] = useState('');

  const items = ['apple', 'banana', 'grape', 'orange'];
  const filteredItems = useMemo(() => items.filter(item => item.includes(filter)), [filter]);

  return (
    <div>
      <button onClick={() => setCount(c => c + 1)}>Count: {count}</button>
      <input
        type="text"
        placeholder="Filter items"
        value={filter}
        onChange={e => setFilter(e.target.value)}
      />
      <Child items={filteredItems} />
    </div>
  );
}

export default App;
```

## 6. `useReducer`

### Explanation:

`useReducer` is a React Hook that provides a more predictable way to manage complex state logic. It’s an alternative to `useState` and is particularly useful when state transitions depend on previous state or involve multiple sub-values.

### Syntax:

```jsx
const [state, dispatch] = useReducer(reducer, initialState);
```

### Key Points:

- **Reducer Function**: A pure function that takes the current `state` and an `action` and returns the new state.
- **Dispatch Function**: A function to send actions to the reducer to update the state.
- **Initial State**: Can be a value or a function to lazily initialize state.

### Common Use Cases:

1. **Managing complex state with multiple sub-values**
2. **Centralizing state transitions (like Redux in a smaller scope)**
3. **Handling user actions with more clarity and scalability**

### Example:

#### Basic Counter Example:

```jsx
import React, { useReducer } from 'react';

// Reducer function
const reducer = (state, action) => {
  switch (action.type) {
    case 'increment':
      return { count: state.count + 1 };
    case 'decrement':
      return { count: state.count - 1 };
    case 'reset':
      return { count: 0 };
    default:
      throw new Error(`Unknown action: ${action.type}`);
  }
};

function Counter() {
  const [state, dispatch] = useReducer(reducer, { count: 0 });

  return (
    <div>
      <p>Count: {state.count}</p>
      <button onClick={() => dispatch({ type: 'increment' })}>+</button>
      <button onClick={() => dispatch({ type: 'decrement' })}>-</button>
      <button onClick={() => dispatch({ type: 'reset' })}>Reset</button>
    </div>
  );
}

export default Counter;
```

#### Managing Complex State:

```jsx
import React, { useReducer } from 'react';

// Reducer function
const reducer = (state, action) => {
  switch (action.type) {
    case 'add_todo':
      return { ...state, todos: [...state.todos, action.payload] };
    case 'remove_todo':
      return { ...state, todos: state.todos.filter((_, idx) => idx !== action.index) };
    case 'toggle_theme':
      return { ...state, darkMode: !state.darkMode };
    default:
      throw new Error(`Unknown action: ${action.type}`);
  }
};

function TodoApp() {
  const [state, dispatch] = useReducer(reducer, { todos: [], darkMode: false });
  const [newTodo, setNewTodo] = React.useState('');

  return (
    <div style={{ background: state.darkMode ? '#333' : '#fff', color: state.darkMode ? '#fff' : '#000' }}>
      <h1>Todo List</h1>
      <input
        type="text"
        value={newTodo}
        onChange={e => setNewTodo(e.target.value)}
      />
      <button onClick={() => {
        dispatch({ type: 'add_todo', payload: newTodo });
        setNewTodo('');
      }}>
        Add Todo
      </button>
      <button onClick={() => dispatch({ type: 'toggle_theme' })}>
        Toggle Theme
      </button>
      <ul>
        {state.todos.map((todo, index) => (
          <li key={index}>
            {todo} <button onClick={() => dispatch({ type: 'remove_todo', index })}>Remove</button>
          </li>
        ))}
      </ul>
    </div>
  );
}

export default TodoApp;
```

## 7. `useCallback`

### Explanation:

`useCallback` is a React Hook that memoizes a function, ensuring it remains the same between renders unless its dependencies change. It is particularly useful for optimizing performance when passing callback functions to child components, as it prevents unnecessary re-creation of functions.

### Syntax:

```jsx
const memoizedCallback = useCallback(() => { /* function logic */ }, [dependencies]);
```

### Key Points:

- **Memoized Function**: The function created with `useCallback` is re-created only when one of the dependencies changes.
- **Performance Optimization**: Reduces unnecessary re-renders, especially in child components that depend on the callback.
- **Dependency Array**: Specifies the variables that the callback depends on. The function is updated if these dependencies change.
- **Avoid Overuse**: Only use `useCallback` if a function is being passed to a child component or used in a performance-critical context.

### Common Use Cases:

1. **Passing stable callback functions to child components**
2. **Avoiding re-creation of event handlers on every render**
3. **Optimizing use with `React.memo`**

### Example:

#### Preventing Unnecessary Re-renders:

```jsx
import React, { useState, useCallback } from 'react';

const Child = React.memo(({ onClick }) => {
  console.log('Child rendered');
  return <button onClick={onClick}>Click Me</button>;
});

function Parent() {
  const [count, setCount] = useState(0);

  // Without useCallback, this function is re-created on every render
  const handleClick = useCallback(() => {
    console.log('Button clicked');
  }, []); // Dependencies: This callback does not depend on anything external

  return (
    <div>
      <p>Parent Count: {count}</p>
      <button onClick={() => setCount(c => c + 1)}>Increment Count</button>
      <Child onClick={handleClick} />
    </div>
  );
}

export default Parent;
```

Optimizing Event Handlers:

```jsx
import React, { useState, useCallback } from 'react';

function Counter() {
  const [count, setCount] = useState(0);

  const increment = useCallback(() => {
    setCount(prevCount => prevCount + 1);
  }, []); // Dependencies: No external dependencies, so remains stable

  return (
    <div>
      <p>Count: {count}</p>
      <button onClick={increment}>Increment</button>
    </div>
  );
}

export default Counter;
```