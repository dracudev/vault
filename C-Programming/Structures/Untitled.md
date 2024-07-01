In C programming, a struct (short for structure) is a composite data type that allows you to group together variables of different data types under a single name. It enables you to create your own data types that can hold multiple pieces of related information.

### Declaring a Struct

To declare a struct, you use the `struct` keyword followed by a struct tag (name of the structure) and a list of member variables enclosed in curly braces `{}`. Here's an example:

`struct Person {`
    `char name[50];`
    `int age;`
    `float height;`
`};`

In this example:

- `struct Person` is the tag or name of the structure.
- `name`, `age`, and `height` are member variables (also called fields or members) of the struct.
- `char name[50]`, `int age`, and `float height` are the data types of each member variable.

### Using a Struct

Once you have defined a struct, you can create variables of that struct type and access its members using the dot `.` operator. Here’s how you might use the `struct Person` example:

`struct Person person1;`

`// Access and assign values to struct members`
`strcpy(person1.name, "John");`
`person1.age = 30;`
`person1.height = 1.75;`

`// Print struct members`
`printf("Name: %s\n", person1.name);`
`printf("Age: %d\n", person1.age);`
`printf("Height: %.2f meters\n", person1.height);`

### Typedef for Structs

In C, you can use `typedef` to create an alias for a struct type, making it easier to declare variables of that type without using the `struct` keyword repeatedly:

`typedef struct {`
    `char make[20];`
    `int year;`
    `float price;`
`} Car;`

Now, you can declare variables of type `Car` directly:

`Car myCar;`
`myCar.year = 2023;`

### Nested Structs

Structs can also be nested within each other to create more complex data structures. Here's an example:

`struct Address {`
    `char city[50];`
    `char street[50];`
    `int zip_code;`
`};`

`struct Employee {`
    `char name[50];`
    `int age;`
    `struct Address address; // Nested struct`
`};`

### Summary

- Structs in C allow you to group variables of different data types into a single unit.
- They are useful for organizing and representing complex data structures.
- Member variables are accessed using the dot `.` operator.
- Typedef can be used to create aliases for structs for easier declaration.
- Nested structs allow you to combine multiple structs to represent hierarchical data.

Structs provide a fundamental building block for organizing data in C programs, offering flexibility and clarity in data representation.