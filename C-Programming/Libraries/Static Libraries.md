Static libraries are collections of object files bundled together into a single file. They are linked into a program at compile time, resulting in a self-contained executable that does not require the library to be present at runtime.

- **Compile Your Source Files**: First, compile your source files (`*.c`) that contain the implementations of your functions into object files (`*.o`). This can be done separately using a `Makefile` or compilation commands like `gcc -c`. This will generate object files `function1.o`, `function2.o`, and `function3.o`.

```bash
gcc -c function1.c function2.c function3.c
```
    
- **Create the Library Archive**: Combine these object files into a static library using the `ar` command.
    
    - **Command**: `ar rcs libft.a *.o`
    - **Explanation**:
        - `ar`: Command to create the library.
        - `-c`: Create the library if it doesn't exist.
        - `-r`: Insert `*.o` files into the library.
        - `-s`: Index the library.
```bash
ar rcs libft.a function1.o function2.o function3.o
```
### Using Static Libraries

Programs that use your static library (`libft.a`) need to include the header files (`libft.h`) where the function prototypes are declared.

1. **Include Header Files**: Ensure your programs include the header file where the function prototypes are declared.
```c
#include "libft.h"
```

2. **Compile and Link with the Static Library**: Compile your programs separately and link them with the static library. Use `-L` to specify the library's location and `-l<name>` to indicate the library name (e.g., `-lft` for `libft.a`).
```c
gcc -o main main.c -L. -lft -I.
```

- `-o main`: The executable file will be named `main`.
- `main.c`: The source file containing the `main` function.
- `-L.`: Specifies that the static library `libft.a` is in the current directory.
- `-lft`: Links the static library `libft.a`.
- `-I.`: Specifies that the header files (`libft.h`) are in the current directory. 