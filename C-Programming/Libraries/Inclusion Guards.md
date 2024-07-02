Inclusion guards are preprocessor directives used to prevent a header file from being included multiple times in the same file. This helps avoid problems like redefinition of types and variables.

### How Inclusion Guards Work

1. **#ifndef**: Checks if a specific identifier has not been defined.
2. **#define**: Defines the identifier if it hasn't been defined previously.
3. **#endif**: Ends the conditional block started by `#ifndef`.
```c
// math_functions.h
#ifndef MATH_FUNCTIONS_H
#define MATH_FUNCTIONS_H

int add(int a, int b);
int subtract(int a, int b);

#endif // MATH_FUNCTIONS_H
```
- `#ifndef MATH_FUNCTIONS_H`: Checks if `MATH_FUNCTIONS_H` is not defined.
- `#define MATH_FUNCTIONS_H`: Defines `MATH_FUNCTIONS_H`.
- `#endif`: Ends the conditional block.