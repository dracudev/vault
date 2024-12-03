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