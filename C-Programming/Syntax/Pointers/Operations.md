### Assignment and Initialization
```c
int *ptr;
int num = 10;
ptr = &num; // Assigning address of num to ptr
```
### Dereferencing
```c
int value = *ptr; // Dereferencing ptr to access value
```
### Adress Arithmetic
```c
ptr++; // Moves pointer to the next memory location (next int)
```
### Null Pointers
```c
int *ptr = NULL; // Initializing ptr as a null pointer
```
### Pointer Arithmetic
```c
int arr[5] = {1, 2, 3, 4, 5};
int *ptr = arr;

// Accessing array elements using pointer arithmetic
for (int i = 0; i < 5; i++) {
    printf("Element %d: %d\n", i, *(ptr + i));
}
```
### Pointer and Functions
Pointers are commonly used in functions to pass and return data efficiently.
```c
void swap(int *a, int *b) {
    int temp = *a;
    *a = *b;
    *b = temp;
}

int main() {
    int x = 5, y = 10;
    swap(&x, &y); // Passing pointers to variables x and y
    printf("x = %d, y = %d\n", x, y); // Output: x = 10, y = 5
    return 0;
}
```
### Pointer and Arrays
Arrays and pointers are closely related in C. An array name can be used as a pointer to its first element.
```c
int arr[5] = {1, 2, 3, 4, 5};
int *ptr = arr; // Pointer to arr[0]

printf("First element: %d\n", *ptr); // Output: 1
printf("Second element: %d\n", *(ptr + 1)); // Output: 2
```

### Pointers and Structs
Struct members are accessed using the arrow (`->`) operator when using pointers to structs.
```c
strcpy(personPtr->name, "John");
personPtr->age = 30;
```