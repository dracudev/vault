Static functions are only accessible within the same source file where they are defined, making them useful for encapsulating helper functions or limiting function scope. To declare a static function, use the `static` keyword before the return type.

```c
static int add(int a, int b) {
    return a + b;
}
```