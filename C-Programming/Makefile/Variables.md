### 1. `@` - Suppressing Command Echoing

The `@` symbol at the beginning of a command in a Makefile suppresses echoing of that particular command to the terminal. This is useful for reducing the clutter in the output when executing the Makefile.
```Makefile
all:
    @echo "Compiling project..."
    $(CC) $(CFLAGS) -o myprog main.c
    @echo "Compilation complete."
```
In this example, the `@` symbol prevents the `echo` commands from being displayed in the terminal output.
### 2. Simple Expansion Variables (`:=`)

Simple expansion variables are variables whose values are expanded at the time of definition. They are evaluated only once, which can be beneficial in avoiding unexpected behavior due to variable expansion timing.
```Makefile
CC := gcc
CFLAGS := -Wall -O2
```
- `:=`: Assigns the value of the variable immediately.
- `CC`: Compiler command (`gcc`).
- `CFLAGS`: Compiler flags (`-Wall -O2`).
### 3. Custom Variables

Custom variables are user-defined variables used to store values that are reused throughout the Makefile. They provide flexibility and allow for easier maintenance by centralizing configurations.
```Makefile
SOURCES := main.c utils.c
OBJECTS := $(SOURCES:.c=.o)
```
- `SOURCES`: List of source files.
- `OBJECTS`: List of object files derived from `SOURCES`.
### 4. Automatic Variables

Automatic variables are predefined variables in Makefiles that are set by `make` for each rule that is executed. They provide information about the target and dependencies of the rule being processed.

- `$@`: The target filename.
- `$<`: The first prerequisite (dependency).
- `$^`: The list of all prerequisites.
- `$*`: The stem of the target filename (without its suffix).