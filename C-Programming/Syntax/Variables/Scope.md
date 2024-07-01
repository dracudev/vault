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

- **Static Variables**: Retain their value between function calls. Local static variables have function scope but persist for the program's lifetime.
```c
void function() {
    static int staticVar = 0; // Static local variable
    staticVar++;
    printf("Static variable: %d\n", staticVar);
}
```