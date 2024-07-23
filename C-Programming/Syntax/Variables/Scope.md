### Local Variables

- **Local Variables**: Declared inside a function or block and accessible only within that function or block.
```c
void function() {
    int localVar = 10; // Local variable
}
```
### Global Variables

- **Global Variables**: Declared outside all functions and accessible from any function within the same file.
```c
int globalVar = 20; // Global variable

void function() {
    globalVar = 30; // Modify global variable
}
```
### Static Variables

A static variable in C is a variable that retains its value between multiple function calls. It is initialized only once and exists for the lifetime of the program, but its scope is limited to the block in which it is defined.

```c
#include <stdio.h>

void count_calls() {
    static int count = 0; // Static variable
    count++;
    printf("Function called %d times\n", count);
}

int main() {
    for (int i = 0; i < 5; i++) {
        count_calls();
    }
    return 0;
}
```
- **Local Static Variables:** Defined within a function and retain their value between calls to that function.
- **Global Static Variables:** Defined outside of all functions and are accessible only within the file in which they are declared.

