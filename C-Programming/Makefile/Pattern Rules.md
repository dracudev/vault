Pattern rules are a way to define rules for multiple targets that follow a pattern. They use `%` as a wildcard.
```Makefile
%.o: %.c
    $(CC) $(CFLAGS) -c $< -o $@
```
- `%`: Matches any sequence of characters.
- `$<`: Automatic variable representing the first prerequisite (source file).
- `$@`: Automatic variable representing the target (object file).