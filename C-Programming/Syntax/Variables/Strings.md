Strings in C are actually arrays of characters. Although using pointers in C is an advanced subject, fully explained later on, we will use pointers to a character array to define simple strings, in the following manner:

```c
char * name = "John Smith";
```

This method creates a string which we can only use for reading. If we wish to define a string which can be manipulated, we will need to define it as a local character array:

```c
char name[] = "John Smith";
```

This notation is different because it allocates an array variable so we can manipulate it. The empty brackets notation `[]` tells the compiler to calculate the size of the array automatically. This is in fact the same as allocating it explicitly, adding one to the length of the string:

```c
char name[] = "John Smith";
/* is the same as */
char name[11] = "John Smith";
```

The reason that we need to add one, although the string `John Smith` is exactly 10 characters long, is for the string termination: a special character (equal to 0) which indicates the end of the string. The end of the string is marked because the program does not know the length of the string - only the compiler knows it according to the code.