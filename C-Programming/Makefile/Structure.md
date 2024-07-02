A Makefile is a special file used by the `make` build automation tool to compile and link programs. It defines how to build the executable from source files, specifying the dependencies and rules for compilation.

## Structure of a Makefile

A Makefile consists of rules with the following structure:
```bash
target: dependencies
    command
```
- **target**: The file to be generated (e.g., executable, object file).
- **dependencies**: Files that the target depends on (e.g., source files, header files).
- **command**: The command to create the target from the dependencies. This line must be indented with a tab.