## Integer Types
- **int**: Used for integers (whole numbers).
```c
int number = 10;
```
- **short**: Used for short integers.
```c
short smallNumber = 5;
```
- **long**: Used for long integers.
```c
long largeNumber = 100000L;
```
- **long long**: Used for long long integers.
```c
long long MIN_INT = -2147483648LL;
```
- **unsigned int**: Used for unsigned integers (only positive values).
```C
unsigned int positiveNumber = 20;
```
- **size_t**: data type defined in the C standard library (`<stddef.h>`) designed to represent the maximum size of an object that can exist in the specific platform where the code runs.
	- In 32-bit systems, it is typically 4 bytes (32 bits), while in 64-bit systems, it is usually 8 bytes (64 bits).
	- Used to express sizes of objects in memory, such as the size of an array or the number of elements in a data structure.
	- Functions like `malloc`, `strlen`, `sizeof` return or take `size_t` as arguments to express sizes.
```c
size_t length = 0;
```

## Floating-Point Types

- **float**: Used for single precision floating-point numbers.
```c
float pi = 3.14f;
```
- **double**: Used for double precision floating-point numbers.
```c
double precisePi = 3.141592653589793;
```
- **long double**: Used for extended precision floating-point numbers.
```c
long double veryPrecisePi = 3.14159265358979323846L;
```

## Character Type

- **char**: Used for single characters.
```c
char letter = 'A';
```