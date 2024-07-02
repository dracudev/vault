The following line:

```c
char * name = "John";
```

does three things:

1. It allocates a local (stack) variable called `name`, which is a pointer to a single character.
2. It causes the string "John" to appear somewhere in the program memory (after it is compiled and executed, of course).
3. It initializes the `name` argument to point to where the `J` character resides at (which is followed by the rest of the string in the memory).

If we try to access the `name` variable as an array, it will work, and will return the ordinal value of the character `J`, since the `name` variable actually points exactly to the beginning of the string.

Since we know that the memory is sequential, we can assume that if we move ahead in the memory to the next character, we'll receive the next letter in the string, until we reach the end of the string, marked with a null terminator (the character with the ordinal value of 0, noted as `\0`).