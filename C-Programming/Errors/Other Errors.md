#### Memory Leaks
- Occur when dynamically allocated memory is not properly deallocated.
- Lead to wasted memory over time, potentially affecting program performance.
- Example:
```c
  void func() {
      int *ptr = malloc(100 * sizeof(int));
      // Forgot to free(ptr);
  }
```
#### Null Pointer Dereference
- Occurs when a null pointer is dereferenced (accessed or modified).
- Leads to a segmentation fault if not handled properly.
- Example:
  ```c
  int *ptr = NULL;
  *ptr = 10;  // Dereferencing NULL pointer
  ```

#### Buffer Overflow
- Occurs when data is written beyond the bounds of a fixed-size buffer.
- Can lead to memory corruption or security vulnerabilities.
- Example:
```c
char buffer[10]; strcpy(buffer, "This string is too long for the buffer"); // Buffer overflow
```

#### Division by Zero
- Occurs when dividing a number by zero.
- Results in an exception or error, depending on the platform.
- Example:
```c
  int a = 10;
  int b = 0;
  int result = a / b;  // Division by zero
```
#### Uninitialized Variables
- Occurs when using variables that have not been assigned a value.
- Leads to unpredictable behavior and bugs in the program.
- Example:
```c
  int x;
  printf("%d\n", x);  // Using uninitialized variable x
```
#### Race Conditions
- Occur in concurrent programs when multiple threads or processes access shared data concurrently.
- Lead to unpredictable behavior depending on timing and execution order.
- Example:
```c
  int global_variable = 0;

  void increment_global() {
      global_variable++;
  }

  void decrement_global() {
      global_variable--;
  }
```

#### Logical Errors
- Occur due to mistakes in the program's logic.
- Cause incorrect program behavior or produce incorrect results.
- Example:
```c
  // Incorrect logic: checking for inequality instead of equality
  if (x != y) {
      printf("x and y are not equal\n");
  }
```

