## 1. **Using `if` Statements**

React does not allow returning multiple elements from a component directly with `if` statements. Instead, we can use `if` statements within the body of the component function to return different JSX conditionally. 
### Example: 
```jsx
function Greeting({ isLoggedIn }) {
	if (isLoggedIn) {
		return <h1>Welcome Back!</h1>; 
	} 
	return <h1>Please Log In</h1>; 
	}
```

## 2. **Using Ternary Operator**

The ternary operator (`condition ? expr1 : expr2`) is a shorthand for `if-else` and is commonly used for conditional rendering in JSX. It returns one of two elements depending on the condition.

### Syntax:

```jsx
condition ? <element1 /> : <element2 />
```
### Example:

```jsx
function Greeting({ isLoggedIn }) {
	return isLoggedIn ? <h1>Welcome Back!</h1> : <h1>Please Log In</h1>; 
}
```

## 3. **Using Logical `&&` (AND) Operator**

The logical `&&` operator is useful when you want to render something **only if a condition is true**. If the condition is false, nothing is rendered.

### Syntax:

```jsx
condition && <element />
```
### Example:

```jsx
function Message({ isLoggedIn }) {
	return (
	    <div>
		    {isLoggedIn && <p>Welcome to the app!</p>}     
	    </div>   
	); 
}
```

In the example above, if `isLoggedIn` is `true`, the paragraph is rendered. If it's `false`, nothing is rendered.

## 4. **Using `switch` Statement**

For more complex conditional rendering based on multiple conditions, the `switch` statement can be used. This is especially helpful when you have several different states to handle.

### Example:
```jsx
function Status({ status }) {
  switch (status) {
    case 'loading':
      return <p>Loading...</p>;
    case 'error':
      return <p>Error occurred</p>;
    case 'success':
      return <p>Data loaded successfully!</p>;
    default:
      return <p>Unknown status</p>;
  }
}
```

## 5. **Inline Conditional Rendering with Functions**

You can create a helper function to handle conditional rendering and call it within your component.

### Example:

```jsx
function Greeting({ isLoggedIn }) {
  const renderMessage = () => {
    if (isLoggedIn) {
      return <h1>Welcome Back!</h1>;
    }
    return <h1>Please Log In</h1>;
  };

  return renderMessage();
}
```