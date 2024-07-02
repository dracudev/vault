Make has built-in rules for common tasks like compiling `.c` files to `.o` files. You can take advantage of these rules to simplify your Makefile.
```Makefile
# Example Makefile with Implicit Rules

# Variables
CC = gcc
CFLAGS = -Wall -g

# Targets and dependencies
main: main.o libmath.a
    $(CC) $(CFLAGS) -o main main.o -L. -lmath

libmath.a: math_functions.o
    ar rcs libmath.a math_functions.o

# Clean up
clean:
    rm -f main main.o libmath.a math_functions.o

```
`main.o` and `math_functions.o` are built using implicit rules.

- The rule for compiling `.c` files to `.o` files is built-in, so you don't need to explicitly write it.