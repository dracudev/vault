## **1. Setting Up React Router**

To use React Router, wrap your application in a `<BrowserRouter>` in your main entry point.
- **`<BrowserRouter>`**: Provides routing context to your application.
- Always place `<BrowserRouter>` at the root of your component tree.

```jsx
import { BrowserRouter } from 'react-router-dom';
import { createRoot } from 'react-dom/client';
import App from './App';

createRoot(document.getElementById('root')).render(
  <BrowserRouter>
    <App />
  </BrowserRouter>
);
```

## **2. Defining Routes**

Use the `<Routes>` and `<Route>` components to define paths and their corresponding components.
- **`<Routes>`**: Contains a collection of `<Route>` components.
- **`<Route>`**: Maps a path to a React component.
    - `path`: The URL path for the route.
    - `element`: The React component to render for the specified path.

```jsx
import { Route, Routes } from "react-router-dom";

function App() {
  return (
    <Routes>
      <Route path="/" element={<Home />} />
      <Route path="/contact" element={<Contact />} />
    </Routes>
  );
}
```


## **3. Navigation with Links**

To navigate between routes, use the `<Link>` component. This avoids full page reloads.
- **`<Link>`**: Allows navigation to a route when clicked.
	- `to`: The destination path.

```jsx
import { Link } from "react-router-dom";

export function Component() {
  return (
    <Link to="/">
      <button>Home</button>
    </Link>
  );
}
```


## **4. Navigation with `useNavigate`**

For programmatic navigation (e.g., after an event or condition), use the `useNavigate` hook.
- **`useNavigate`**: Returns a function to navigate programmatically.
	- `navigate(path)`: Navigates to the specified path.

```jsx
import { useNavigate } from "react-router-dom";

function ExampleComponent() {
  const navigate = useNavigate();

  const handleClick = () => {
    navigate("/contact");
  };

  return <button onClick={handleClick}>Go to Contact</button>;
}
```


## **5. Accessing Route Parameters with `useParams`**

To access dynamic parameters in a route, use the `useParams` hook.

```jsx
import { useParams } from "react-router-dom";

function UserProfile() {
  const { userId } = useParams(); // Extract the dynamic parameter

  return <h1>User ID: {userId}</h1>;
}
```

- **`useParams`**: Returns an object of key-value pairs for dynamic route parameters.

```jsx
<Route path="/user/:userId" element={<UserProfile />} />
```


## **6. Query Parameters with `useSearchParams`**

For handling query parameters in URLs, use the `useSearchParams` hook.
- **`useSearchParams`**: Returns the current query parameters and a function to update them.
	- `searchParams.get(key)`: Retrieves the value for a specific query parameter.
	- `setSearchParams({ key: value })`: Updates query parameters in the URL.

```jsx
import { useSearchParams } from "react-router-dom";

function FilteredList() {
  const [searchParams, setSearchParams] = useSearchParams();
  const category = searchParams.get("category");

  const updateCategory = (newCategory) => {
    setSearchParams({ category: newCategory });
  };

  return (
    <div>
      <h1>Category: {category}</h1>
      <button onClick={() => updateCategory("books")}>Books</button>
      <button onClick={() => updateCategory("movies")}>Movies</button>
    </div>
  );
}
```

## **7. Acceding current URL with `useLocation`**

The `useLocation` hook in React Router is used to access the current location object, which represents where the app is now, including information about the URL path, search parameters, and hash fragment.

Here's a step-by-step explanation of how `useLocation` works:

1. **Import the Hook**: First, you need to import `useLocation` from `react-router-dom`.
2. **Call the Hook**: Inside your functional component, call `useLocation` to get the current location object.
3. **Access Location Properties**: The location object contains properties such as `pathname`, `search`, and `hash` that you can use to get information about the current URL.

Here's an example:

```tsx
import { useLocation } from 'react-router-dom';

const MyComponent = () => {
  const location = useLocation();

  console.log(location.pathname); // Current path
  console.log(location.search);   // Query string
  console.log(location.hash);     // Hash fragment

  return (
    <div>
      <p>Current Path: {location.pathname}</p>
      <p>Query String: {location.search}</p>
      <p>Hash Fragment: {location.hash}</p>
    </div>
  );
};
```

In this example:

- `location.pathname` gives you the current path (e.g., `/home`).
- `location.search` gives you the query string (e.g., `?name=John`).
- `location.hash` gives you the hash fragment (e.g., `#section1`).

This hook is useful for accessing and reacting to changes in the URL within your components.