Header files in C are used to declare the interfaces to functions and macros. They contain definitions for functions, data types, and macros that can be shared across multiple source files.

## Benefits of Using Header Files

- **Modularity**: Separate declarations from implementations.
- **Reusability**: Functions and macros can be reused across multiple programs.
- **Readability**: Improve the organization and readability of your code.

## Creating a Header File

### Step 1: Write Function Prototypes and Macros

A header file typically contains:

- Function prototypes
- Macro definitions
- Type definitions (typedefs)
- Structure declarations
```c
#ifndef MATH_FUNCTIONS_H
#define MATH_FUNCTIONS_H

// Function prototypes
int add(int a, int b);
int subtract(int a, int b);

// Macro definitions
#define PI 3.14159

#endif // MATH_FUNCTIONS_H
```
- `#ifndef MATH_FUNCTIONS_H` and `#define MATH_FUNCTIONS_H`: Inclusion guards to prevent multiple inclusions.
- Function prototypes: Declare the functions `add` and `subtract`.
- Macro definitions: Define `PI`.

## Using a Header File

### Step 2: Implement the Functions

Write the corresponding source file that implements the functions declared in the header file.

```c
#include "math_functions.h"

int add(int a, int b) {
    return a + b;
}

int subtract(int a, int b) {
    return a - b;
}
```

### Step 3: Include the Header File in Your Program

To use the functions and macros declared in the header file, include it in your program.
```c
#include <stdio.h>
#include "math_functions.h"

int main() {
    int a = 5, b = 3;

    printf("Add: %d + %d = %d\n", a, b, add(a, b));
    printf("Subtract: %d - %d = %d\n", a, b, subtract(a, b));
    printf("PI: %f\n", PI);

    return 0;
}
```

### Step 4: Compile and Link

Compile the source files and link them together.
```
gcc -c math_functions.c
gcc -o main main.c math_functions.o
```
- `gcc -c math_functions.c`: Compile `math_functions.c` into an object file.
- `gcc -o main main.c math_functions.o`: Compile `main.c` and link it with `math_functions.o`.