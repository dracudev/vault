Variadic functions in C are functions that can accept a variable number of arguments. This feature is particularly useful when the number of arguments needed by a function is not fixed.

```c
#include <stdarg.h>

return_type function_name(int fixed_arg, ...);
```

```c
#include <stdio.h>
#include <stdarg.h>

// Variadic function to calculate the sum of integers
int sum(int num_args, ...) {
    va_list args;
    int total = 0;

    // Initialize va_list with variable arguments
    va_start(args, num_args);

    // Loop through all variable arguments
    for (int i = 0; i < num_args; i++) {
        total += va_arg(args, int); // Retrieve each argument
    }

    // Clean up va_list
    va_end(args);

    return total;
}

int main() {
    int result1 = sum(3, 10, 20, 30); // Sum of 10 + 20 + 30
    printf("Sum 1: %d\n", result1);

    int result2 = sum(5, 1, 2, 3, 4, 5); // Sum of 1 + 2 + 3 + 4 + 5
    printf("Sum 2: %d\n", result2);

    return 0;
}
```