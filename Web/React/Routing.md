```jsx
import { BrowserRouter } from 'react-router-dom';

createRoot(document.getElementById('root')).render(
  <BrowserRouter>
    <App />
  </BrowserRouter>,
)
```

```jsx
import { Route, Routes } from "react-router-dom";

function App() {
  return (
    <Routes>
      <Route path="/" element={<Home/>}></Route>
      <Route path="/contact" element={<Contact/>}></Route>
    </Routes>
  );
}
```

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

### States on URL

```jsx
import { useSearchParams } from "react-router";

export function SomeComponent() {
  const [searchParams, setSearchParams] = useSearchParams();
  // ...
}
```