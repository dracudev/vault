Inline functions are defined using the `inline` keyword and suggest to the compiler to insert the function's code directly into the caller to reduce function call overhead.

```c
inline int square(int x) {
    return x * x;
}
```