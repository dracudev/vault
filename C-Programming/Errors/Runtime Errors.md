#### Segmentation Fault (Segfault)
- Occurs when a program accesses memory it shouldn't.
- Common causes include dereferencing NULL pointers, accessing out-of-bounds memory, or writing to read-only memory.
- Example scenarios:
  - Dereferencing a NULL pointer: `int *ptr = NULL; *ptr = 10;`
  - Accessing out-of-bounds array index: `int arr[5]; arr[10] = 5;`
  - Writing to a string literal: `char *str = "Hello"; str[0] = 'h';`
#### Bus Error
- Occurs when a program tries to access misaligned memory or memory it can't access.
- Often due to hardware-specific memory alignment issues.
- Example scenarios:
  - Misaligned memory access: Trying to access a 4-byte integer at an address that is not a multiple of 4.
  - Accessing memory outside the allowed address space.
#### Stack Overflow
- Occurs when the call stack exceeds its allocated size.
- Common causes include excessive recursion or allocating large data structures on the stack.
- Example scenarios:
  - Excessive recursion: A function calls itself repeatedly without terminating.
  - Large local variables: Declaring large arrays or structures as local variables.
#### Floating Point Exception (FPE)
- Occurs when an arithmetic operation on floating-point numbers results in an undefined or unexpected value.
- Common causes include division by zero or invalid operations like NaN.
- Example scenarios:
  - Division by zero: `float result = 1.0 / 0.0;`
  - Invalid floating-point operation: `float result = sqrt(-1.0);`
#### Double Free
- Occurs when a program attempts to free a memory block that has already been freed.
- Can lead to memory corruption and program crashes.
- Common causes:
  - Freeing the same pointer multiple times: `free(ptr); free(ptr);`
  - Freeing part of a pointer and then the whole block: 
    ```c
    void *ptr = malloc(10 * sizeof(int));
    free(ptr + 5);  // Incorrect: frees part of the allocated block
    free(ptr);       // Incorrect: attempts to free the entire block again
    ```
- Example scenarios:
  - Incorrectly managing memory allocation and deallocation in complex data structures.
  - Using pointers to freed memory without checking if they are still valid.
