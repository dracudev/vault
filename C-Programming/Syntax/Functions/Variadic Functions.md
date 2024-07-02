Variadic functions in C are functions that can accept a variable number of arguments. This feature is particularly useful when the number of arguments needed by a function is not fixed.

To define a variadic function, you need to include the `stdarg.h` header and use the following macros:

1. `va_list`: A type to hold information about variable arguments.
2. `va_start`: Initializes a `va_list` variable to retrieve the additional arguments.
3. `va_arg`: Retrieves the next argument in the list.
4. `va_copy`: duplicates a `va_list` variable, allowing you to traverse the arguments multiple times if needed. 
5. `va_end`: Cleans up the `va_list` variable.

```c
#include <stdarg.h>

return_type function_name(int fixed_arg, ...);
```

```c
#include <stdarg.h>
#include <stdio.h>

// Variadic function to calculate the sum of integers
int sum(int count, ...) {
    va_list args1, args2;
    int total1 = 0, total2 = 0;

    // Initialize the first va_list variable
    va_start(args1, count);

    // Copy the va_list to a second variable
    va_copy(args2, args1);

    // Loop through the arguments using the first va_list
    for (int i = 0; i < count; i++) {
        total1 += va_arg(args1, int); // Retrieve the next argument
    }

    // Loop through the arguments again using the second va_list
    for (int i = 0; i < count; i++) {
        total2 += va_arg(args2, int); // Retrieve the next argument
    }

    // Clean up the va_list variables
    va_end(args1);
    va_end(args2);

    // For demonstration, we'll just return the first total calculated
    return total1;
}

int main() {
    printf("Sum of 1, 2, 3: %d\n", sum(3, 1, 2, 3)); // Output: 6
    printf("Sum of 4, 5, 6, 7: %d\n", sum(4, 4, 5, 6, 7)); // Output: 22
    return 0;
}
```