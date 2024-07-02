The `malloc` function in C is used to allocate memory dynamically during program execution. It reserves a specified number of bytes from the heap and returns a pointer to the beginning of the allocated memory block.
```c
#include <stdlib.h>

int *ptr = (int *)malloc(10 * sizeof(int));
if (ptr == NULL) {
    // Handle allocation failure
    perror("malloc");
    exit(EXIT_FAILURE);
}
```
- **Protection**: Always check if `malloc` returns `NULL` to handle allocation failures gracefully. This is crucial for preventing crashes due to insufficient memory.

The `free` function deallocates dynamically allocated memory previously allocated by `malloc`, `calloc`, or `realloc`. It makes the memory block available for reuse.
```c
free(ptr);
ptr = NULL; // Optional: Prevents dangling pointers
```
- **Protection**: After calling `free`, set the pointer to `NULL` to prevent accessing freed memory, which could lead to undefined behavior.
