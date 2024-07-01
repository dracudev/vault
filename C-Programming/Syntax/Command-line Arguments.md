In C programming, `argc` and `argv` are parameters passed to the `main` function when a program is executed from the command line. They are used to handle command-line arguments, allowing programs to accept inputs directly from the user at runtime.
## `argc` (Argument Count)

`argc` is an integer variable that represents the number of arguments passed to the program from the command line, including the name of the program itself.

```c
int main(int argc, char **argv) {
    // Code goes here
}
```
- **argc**: Contains the number of command-line arguments passed to the program.
- **argv**: An array of strings (`char **argv`) where each element is a pointer to a string that represents a command-line argument.

## `argv` (Argument Vector)

`argv` is an array of strings (`char **argv`) where each element points to a string that represents a command-line argument.

```c
int main(int argc, char **argv) {
    for (int i = 0; i < argc; i++) {
        printf("Argument %d: %s\n", i, argv[i]);
    }
    return 0;
}
```
- **argv[0]**: Points to the name of the program itself.
- **argv[1] to argv[argc-1]**: Point to the actual command-line arguments passed to the program.
	- argv[argc - 1] : is the last index
- argc 1 = /a.out (starts from 1)
- argv[0] = /a.out (starts from 0)
