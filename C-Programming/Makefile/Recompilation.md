Make intelligently determines which parts of the project need to be recompiled based on the timestamps of files. If a dependency is newer than the target, the target will be rebuilt.

### Example

If `math_functions.c` or `math_functions.h` is modified, running `make` will recompile `math_functions.o` and then relink `libmath.a` and `main`.