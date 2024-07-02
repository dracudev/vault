An array is a collection of variables that are accessed with an index number. All elements of an array have the same type, which can be a built-in type like `int`, `float`, `char`, or a user-defined type.
## Declaring and Initializing Arrays

### Declaration

To declare an array, you specify the type of its elements and the number of elements required. The syntax for declaring an array is:
```c
type arrayName[arraySize];

int numbers[5]; // Declares an array of 5 integers
```
- `type` is the data type of the elements.
- `arrayName` is the name of the array.
- `arraySize` is the number of elements in the array.
### Initialization

You can initialize an array at the time of declaration using curly braces `{}`.
```c
int numbers[5] = {1, 2, 3, 4, 5};
int numbers[] = {1, 2, 3, 4, 5}; // Size is automatically set to 5
int numbers[5] = {1, 2}; // Initializes to {1, 2, 0, 0, 0}
```

## Accessing Array Elements

Array elements are accessed using the index number. The index of the first element is 0.
```c
int numbers[5] = {1, 2, 3, 4, 5};

int first = numbers[0]; // Accesses the first element, which is 1
int third = numbers[2]; // Accesses the third element, which is 3
```

## Modifying Array Elements

Array elements can be modified using their index.
```c
int numbers[5] = {1, 2, 3, 4, 5};

numbers[0] = 10; // Modifies the first element to 10
numbers[2] = 30; // Modifies the third element to 30
```

## Multidimensional Arrays

C supports multidimensional arrays. The most common are two-dimensional arrays, which can be visualized as a matrix or table.
```c
int matrix[3][3] = {
    {1, 2, 3},
    {4, 5, 6},
    {7, 8, 9}
};
```
### Accessing Elements

Elements in a two-dimensional array are accessed using two indices.
```c
int value = matrix[1][2]; // Accesses the element in the second row, third column (which is 6)
```

### Modifying Elements

Elements can be modified similarly.
```c
matrix[0][0] = 10; // Modifies the first element to 10
matrix[2][1] = 80; // Modifies the element in the third row, second column to 80
```