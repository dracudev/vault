### Function Definition

A function definition provides the actual body of the function.
```c
return_type function_name(parameter_list) {
    // Function body
}

int add(int a, int b) {
    return a + b;
}
```

## Function Call

To use a function, you call it by its name, passing the required arguments.
```c
result = function_name(arguments);

int sum = add(5, 3); // sum will be 8
```

## Parameter Passing

### Pass by Value

C functions use pass-by-value by default. This means the function receives a copy of the argument's value, and changes to the parameter do not affect the original argument.
```c
void modifyValue(int x) {
    x = 10; // This change will not affect the original argument
}

int main() {
    int a = 5;
    modifyValue(a);
    printf("%d\n", a); // Output: 5
    return 0;
}
```

### Pass by Reference

To modify the original argument, you can pass a pointer to the variable.
```c
void modifyValue(int *x) {
    *x = 10; // This change will affect the original argument
}

int main() {
    int a = 5;
    modifyValue(&a);
    printf("%d\n", a); // Output: 10
    return 0;
}
```
## Return Statement

The `return` statement ends function execution and optionally returns a value to the caller.
```c
return value;

int add(int a, int b) {
    return a + b;
}
```