Fetching data in Next.js can be done in both server and client components. Server-side fetching is the default approach for **React Server Components (RSCs)**, ensuring better performance and SEO.

#### Fetching with `async/await` in Server Components

Server Components (files in the `app/` directory) can directly use `async/await` for data fetching without additional hooks.

```tsx
// app/dashboard/page.tsx
async function fetchData() {
  const res = await fetch('https://api.example.com/data');
  if (!res.ok) throw new Error('Failed to fetch data');
  return res.json();
}

export default async function DashboardPage() {
  const data = await fetchData();

  return (
    <div>
      <h1>Dashboard</h1>
      <pre>{JSON.stringify(data, null, 2)}</pre>
    </div>
  );
}
```

#### Fetching in Client Components

For client-side fetching, you can use hooks like `useState` and `useEffect` or libraries like `SWR` or `React Query`.

```tsx
'use client';

import { useState, useEffect } from 'react';

export default function ClientComponent() {
  const [data, setData] = useState(null);

  useEffect(() => {
    async function fetchData() {
      const res = await fetch('https://api.example.com/data');
      const json = await res.json();
      setData(json);
    }

    fetchData();
  }, []);

  return (
    <div>
      <h1>Client-Side Data</h1>
      {data ? <pre>{JSON.stringify(data, null, 2)}</pre> : <p>Loading...</p>}
    </div>
  );
}
```

### React Server Components (RSCs)

RSCs allow fetching data on the server and rendering it directly, eliminating the need for hydration on the client.
#### Benefits of RSCs

- **Improved Performance**: Fetch data closer to the server.
- **Reduced JavaScript**: Less code sent to the client.
- **SEO-Friendly**: Fully rendered HTML is sent to search engines.

```tsx
// app/products/page.tsx
async function fetchProducts() {
  const res = await fetch('https://api.example.com/products');
  return res.json();
}

export default async function ProductsPage() {
  const products = await fetchProducts();

  return (
    <div>
      <h1>Products</h1>
      <ul>
        {products.map((product: { id: number; name: string }) => (
          <li key={product.id}>{product.name}</li>
        ))}
      </ul>
    </div>
  );
}
```

### `loading.tsx` and Skeletons

The `loading.tsx` file provides a built-in way to show a loading state while server-side components or data are being fetched.

```tsx
// app/products/loading.tsx
export default function Loading() {
  return (
    <div>
      <h1>Loading Products...</h1>
    </div>
  );
}
```

This file automatically renders while the `page.tsx` for the route is being prepared.
#### Adding Skeletons

Skeletons provide a placeholder UI during the loading state.

```tsx
// app/products/loading.tsx
export default function Loading() {
  return (
    <div>
      <h1>Loading Products...</h1>
      <ul>
        {Array.from({ length: 5 }).map((_, index) => (
          <li key={index} className="skeleton">
            <div className="skeleton-line"></div>
          </li>
        ))}
      </ul>
    </div>
  );
}
```

### Streaming HTML

Next.js can stream rendered HTML to the client incrementally as it becomes available. This reduces time-to-first-byte and improves perceived performance.
#### Example: Streaming HTML with Suspense

Suspense allows you to defer rendering parts of the UI until data is ready.

```tsx
// app/products/page.tsx
import { Suspense } from 'react';
import ProductList from './ProductList';
import Loading from './loading';

export default function ProductsPage() {
  return (
    <div>
      <h1>Products</h1>
      <Suspense fallback={<Loading />}>
        <ProductList />
      </Suspense>
    </div>
  );
}
```