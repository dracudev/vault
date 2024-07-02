Structures (`structs`) in C allow you to group variables of different types under a single name. This is useful for representing complex data types.

### Declaration

To declare a structure, you use the `struct` keyword followed by the structure name and the body enclosed in braces.
```c
struct Person {
    char name[50];
    int age;
    float height;
};
```

### Defining and Accessing Struct Variables

After declaring a structure, you can define variables of that type.
```c
struct Person person1;
```

You can access and modify the members of a struct using the dot (`.`) operator.
```c
strcpy(person1.name, "Alice");
person1.age = 30;
person1.height = 5.7;
```
### Initialization

Structures can also be initialized at the time of definition.
```c
struct Person person2 = {"Bob", 25, 6.0};
```
