React Query is a data-fetching and state management library for React. It simplifies handling server state by providing tools to fetch, cache, synchronize, and update data in React applications.

### **Key Features**

- Simplifies API requests with minimal boilerplate.
- Built-in caching for performance.
- Automatic background data synchronization.
- Tools for pagination, infinite scrolling, and optimistic updates.

#### Installation

```bash
npm install @tanstack/react-query
```

## **1. Setting Up React Query**

Wrap your application in a `QueryClientProvider` to provide the React Query context.

```tsx
import { QueryClient, QueryClientProvider } from '@tanstack/react-query';

const queryClient = new QueryClient();

function App() {
  return (
    <QueryClientProvider client={queryClient}>
      <YourComponents />
    </QueryClientProvider>
  );
}
```

## **2. Fetching Data with `useQuery`**

The `useQuery` hook is used to fetch and cache data.

```tsx
import { useQuery } from '@tanstack/react-query';

function FetchUser() {
  const { data, isLoading, error } = useQuery(['user'], fetchUser);

  if (isLoading) return <p>Loading...</p>;
  if (error) return <p>Error loading data</p>;

  return <p>{data.name}</p>;
}

async function fetchUser() {
  const response = await fetch('/api/user');
  return response.json();
}
```

### **Key Concepts**

- **`queryKey`**: A unique identifier (array or string) for the query.
- **`queryFn`**: The function used to fetch data.
- **`data`**: The fetched data.
- **`isLoading`**: Boolean indicating loading state.
- **`error`**: Contains error information if the request fails.

##  **3. Mutating Data with `useMutation`**

The `useMutation` hook is used for creating, updating, or deleting data.

```tsx
import { useMutation } from '@tanstack/react-query';

function CreateUser() {
  const mutation = useMutation(addUser);

  const handleAddUser = () => {
    mutation.mutate({ name: 'John Doe' });
  };

  return (
    <button onClick={handleAddUser}>
      {mutation.isLoading ? 'Adding...' : 'Add User'}
    </button>
  );
}

async function addUser(user) {
  const response = await fetch('/api/users', {
    method: 'POST',
    body: JSON.stringify(user),
    headers: { 'Content-Type': 'application/json' },
  });
  return response.json();
}
```

### **Key Concepts**

- **`mutate`**: Triggers the mutation.
- **`isLoading`**: Indicates the mutation is in progress.
- **`onSuccess`**: A callback executed when the mutation succeeds.
- **`onError`**: A callback executed if the mutation fails.

## **4. Query Invalidation**

Queries can be invalidated to force refetching of stale data using the `queryClient.invalidateQueries` method.

```tsx
import { useMutation, useQueryClient } from '@tanstack/react-query';

function DeleteUser({ userId }) {
  const queryClient = useQueryClient();

  const mutation = useMutation(deleteUser, {
    onSuccess: () => {
      queryClient.invalidateQueries(['users']); // Refresh 'users' data
    },
  });

  const handleDelete = () => {
    mutation.mutate(userId);
  };

  return <button onClick={handleDelete}>Delete</button>;
}

async function deleteUser(id) {
  return fetch(`/api/users/${id}`, { method: 'DELETE' });
}
```

## **5. Handling Dependent Queries**

Sometimes, a query depends on the result of another query. Use the `enabled` option to control when a query runs.

```tsx
const { data: user } = useQuery(['user'], fetchUser);
const { data: posts } = useQuery(['posts', user?.id], fetchPosts, {
  enabled: !!user, // Run only after 'user' is fetched
});

async function fetchPosts(userId) {
  const response = await fetch(`/api/posts?userId=${userId}`);
  return response.json();
}
```


## **8. Pagination and Infinite Queries**

```tsx
import { useQuery } from '@tanstack/react-query';

function PaginatedList({ page }) {
  const { data } = useQuery(['posts', page], () => fetchPosts(page));

  return (
    <div>
      {data.posts.map(post => <p key={post.id}>{post.title}</p>)}
      <button onClick={() => setPage(page + 1)}>Next Page</button>
    </div>
  );
}

async function fetchPosts(page) {
  const response = await fetch(`/api/posts?page=${page}`);
  return response.json();
}
```

```tsx
import { useInfiniteQuery } from '@tanstack/react-query';

function InfiniteScrollList() {
  const {
    data,
    fetchNextPage,
    hasNextPage,
  } = useInfiniteQuery(
    ['posts'],
    ({ pageParam = 1 }) => fetchPosts(pageParam),
    {
      getNextPageParam: (lastPage) => lastPage.nextPage, // Logic for next page
    }
  );

  return (
    <div>
      {data.pages.map((group, i) => (
        <React.Fragment key={i}>
          {group.posts.map(post => <p key={post.id}>{post.title}</p>)}
        </React.Fragment>
      ))}
      {hasNextPage && <button onClick={fetchNextPage}>Load More</button>}
    </div>
  );
}
```