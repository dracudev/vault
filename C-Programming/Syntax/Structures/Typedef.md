The `typedef` keyword in C allows you to create new names (aliases) for existing data types. This can make your code more readable and easier to manage.
```c
typedef existing_type new_type_name;
```

By using `typedef`, you can declare variables of type `Person` without having to prefix them with `struct`.

```c
typedef struct Person {
    char name[50];
    int age;
    float height;
} Person;

Person person3;
strcpy(person3.name, "Charlie");
person3.age = 28;
person3.height = 5.8;
```
