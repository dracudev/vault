### Arithmetic Operators

- **Addition**: `+`
```c
int sum = a + b;
```
- **Subtraction**: `-`
```c
int difference = a - b;
```
- **Multiplication**: `*`
```c
int product = a * b;
```
- **Division**: `/`
```c
int quotient = a / b;
```
- **Modulus**: `%`
```c
int remainder = a % b;
```
### Relational Operators

- **Equal to**: `==`
```c
if (a == b) { /* ... */ }
```
- **Not equal to**: `!=`
```c
if (a != b) { /* ... */ }
```
- **Greater than**: `>`
```c
if (a > b) { /* ... */ }
```
- **Less than**: `<`
```c
if (a < b) { /* ... */ }
```
- **Greater than or equal to**: `>=`
```c
if (a >= b) { /* ... */ }
```
- **Less than or equal to**: `<=`
```c
if (a <= b) { /* ... */ }
```

### Autoincrement Operators in C

In C, autoincrement is often associated with two specific operators: `++` (increment) and `--` (decrement). These operators are unary operators, meaning they operate on a single operand.

Autoincrement is commonly used in loops, array traversal, and other scenarios where sequential access or counting is required. It simplifies code and improves readability by combining the increment operation with other operations or assignments.
#### 1. Post-increment (`_++`)

The post-increment operator (`++`) increments the value of a variable after it has been used in an expression. It can be applied to both integer and pointer types.
```c
int a = 5;
int b = a++;   // b gets the value of 'a' (5), then 'a' is incremented to 6
printf("a = %d, b = %d\n", a, b);  // Output: a = 6, b = 5
```

```c
int arr[5] = {1, 2, 3, 4, 5};
int *ptr = arr;
printf("%d\n", *ptr++);  // Prints the value at 'ptr' (1), then 'ptr' is incremented
printf("%d\n", *ptr);    // Prints the next value at 'ptr' (2)
```

#### 2. Pre-increment (`++_`)

The pre-increment operator (`++`) increments the value of a variable before it is used in an expression.
```c
int x = 5;
int y = ++x;   // 'x' is incremented to 6, then 'y' gets the value of 'x' (6)
printf("x = %d, y = %d\n", x, y);  // Output: x = 6, y = 6
```

```c
int arr[5] = {1, 2, 3, 4, 5};
int *ptr = arr;
printf("%d\n", *++ptr);  // 'ptr' is incremented to point to the next element (2), then its value is printed
printf("%d\n", *ptr);    // Prints the value at the new 'ptr' position (2)
```

