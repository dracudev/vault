A function that calls itself is known as a recursive function. Recursive functions must have a base case to avoid infinite recursion.
```c
int factorial(int n) {
    if (n == 0) {
        return 1; // Base case
    } else {
        return n * factorial(n - 1); // Recursive case
    }
}
```