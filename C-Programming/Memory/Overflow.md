- Para evitar el desbordamiento de integers debemos tener en cuenta su máximo y lanzar un error cuando se supere. 
- Por ejemplo en ft_calloc(size_t count, size_t size) nos aseguramos que la multiplicación de ambas variables no supere el size_t máximo --> (size_t) - 1. 
    - `If (size != 0 && n > (size_t) - 1 / size) { return (NULL) }` 
    - En este caso al dividir la máxima expresión de size_t entre size obtendremos el máximo de veces que podemos multiplicar por n sin que haya desbordamiento.

Memory overflow, or buffer overflow, occurs when data is written beyond the boundaries of allocated memory. This can overwrite adjacent memory locations, corrupting data or causing program crashes.
```c
int arr[10];
arr[15] = 10; // Buffer overflow: Writing beyond the allocated memory of arr
```
### Integer Overflow

Integer overflow occurs when an arithmetic operation results in a value that exceeds the maximum representable value for that data type in memory. In C, integer types (like `int`, `short`, `long`, etc.) have fixed ranges defined by the number of bits they occupy (e.g., 32-bit `int` can store values from -2,147,483,648 to 2,147,483,647).

Integer overflow typically occurs under the following circumstances:
- **Arithmetic Operations**: Performing operations that result in a value beyond the maximum or below the minimum representable value for that type.
```c
int a = INT_MAX;   // Maximum value for int
int b = a + 1;     // Integer overflow: Result is undefined behavior
```
- **Increment/Decrement**: Incrementing or decrementing a variable beyond its limits.
```c
unsigned char count = 255;  // Maximum value for unsigned char (typically 255)
count++;                    // Integer overflow: Result is 0 (for unsigned types)
```
- **Multiplication**: Multiplying values where the product exceeds the maximum representable value.
```c
int x = INT_MAX;   // Maximum value for int
int y = 2;
int z = x * y;     // Integer overflow: Result is undefined behavior
```

### Handling Integer Overflow

#### 1. Checking for Potential Overflow

Before performing operations that could potentially overflow, check whether the operation will exceed the limits of the data type.
```c
int a = INT_MAX;
int b = 1;

if (b > 0 && a > INT_MAX - b) {
    // Handle overflow condition
    printf("Integer overflow detected!\n");
} else {
    int result = a + b;
    printf("Result: %d\n", result);
}
```

#### 2. Use Larger Data Types or Library Functions

- Use larger data types (`long`, `long long`) if the range of `int` is insufficient for your calculations.
```c
long long result = (long long)a * b;   // Use long long for larger values
```
#### 3. Compiler Warnings and Options

- Enable compiler warnings (`-Woverflow`) to detect potential overflow situations during compilation.
- Use compiler options (`-fwrapv`) to define the behavior of signed integer overflow as two's complement wraparound.
#### Consequences of Integer Overflow

Integer overflow can lead to undefined behavior, which is unpredictable and can manifest in various ways:

- **Wraparound**: The value wraps around from the maximum to the minimum representable value (for signed types) or from the maximum value to 0 (for unsigned types).
- **Crashes**: The program may crash or produce incorrect results.
- **Security Vulnerabilities**: Integer overflow can lead to security vulnerabilities if not handled properly, such as in buffer overflows.