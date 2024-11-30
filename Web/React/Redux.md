### 1. **Creating a Redux Store with `configureStore`**

`configureStore` is a wrapper around the traditional `createStore` method that simplifies store setup. It automatically includes important middleware like Redux DevTools and Thunk.

### Syntax:

```js
import { configureStore } from '@reduxjs/toolkit';
import userReducer from './userSlice';

const store = configureStore({
  reducer: {
    user: userReducer,
  },
});
```

### 2. **Slices with `createSlice`**

A "slice" is a piece of Redux state along with the reducers and actions that update it. The `createSlice` function is used to generate both actions and reducers in one place.

### Syntax:

```js
import { createSlice } from '@reduxjs/toolkit';

const counterSlice = createSlice({
  name: 'counter',
  initialState: { count: 0 },
  reducers: {
    increment: (state) => {
      state.count += 1;
    },
    decrement: (state) => {
      state.count -= 1;
    },
  },
});

export const { increment, decrement } = counterSlice.actions;
export default counterSlice.reducer;
```


### 3. **Accessing Redux State**

To access the state in your React components, you use the `useSelector` hook from `react-redux`.

### Syntax:

```js
import { useSelector } from 'react-redux';

function Counter() {
  const count = useSelector((state) => state.counter.count);

  return <h1>Count: {count}</h1>;
}
```

### 4. **Dispatching Actions**

To dispatch an action, you can use the `useDispatch` hook from `react-redux`.

### Syntax:

```js
import { useDispatch } from 'react-redux';
import { increment } from './counterSlice';

function Counter() {
  const dispatch = useDispatch();

  return (
    <div>
      <button onClick={() => dispatch(increment())}>Increment</button>
    </div>
  );
}
```

### 5. **Async Actions with `createAsyncThunk`**

`createAsyncThunk` is a helper function that simplifies handling asynchronous actions like data fetching. It generates actions for different stages of the async operation (pending, fulfilled, rejected).

### Syntax:

```js
import { createSlice, createAsyncThunk } from '@reduxjs/toolkit';

export const fetchData = createAsyncThunk(
  'data/fetchData',
  async (url) => {
    const response = await fetch(url);
    return response.json();
  }
);

const dataSlice = createSlice({
  name: 'data',
  initialState: { items: [], loading: false },
  reducers: {},
  extraReducers: (builder) => {
    builder
      .addCase(fetchData.pending, (state) => {
        state.loading = true;
      })
      .addCase(fetchData.fulfilled, (state, action) => {
        state.loading = false;
        state.items = action.payload;
      })
      .addCase(fetchData.rejected, (state) => {
        state.loading = false;
      });
  },
});

export default dataSlice.reducer;
```