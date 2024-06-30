
This Makefile is designed to compile a C library (`libft.a`) from source files and optionally include additional "bonus" source files. It ensures that only modified files are recompiled, and the library is updated without recompiling everything.

## Variables

- **LIB**: The command to create or update the static library. Using `ar`.
- **RM**: The command to remove files. Using `rm -f`.
- **CC**: The C compiler. Using `gcc`.
- **CCFLAGS**: Compiler flags to enable all warnings and treat them as errors.
- **NAME**: The name of the static library to create, `libft.a`.
- **SRC**: The list of source files to compile into the library.
- **OBJ**: The list of object files corresponding to the source files.
- **INCLUDE**: The header file to include in compilation.
- **BONUS_SRC**: The list of bonus source files.
- **BONUS_OBJ**: The list of object files corresponding to the bonus source files.

## Targets

### `all`

This is the default target, which depends on `$(NAME)`. It will create the library if it doesn't exist or if any source files have changed.

### `$(NAME)`

This target creates the static library `libft.a` from the object files `$(OBJ)`. It uses the `ar rcs` command to create the library and index the contents.

### `bonus`

This target compiles the bonus object files `$(BONUS_OBJ)` and adds them to the library `$(NAME)` using the `ar r` command. This ensures that only the modified bonus files are recompiled and added to the library.

### `%.o`

This pattern rule compiles any `.c` file into a corresponding `.o` file, ensuring each object file depends on its source file and the header file `$(INCLUDE)`.

### `clean`

This target removes all object files (both regular and bonus) using the `rm -f` command.

### `fclean`

This target depends on `clean` and also removes the static library `$(NAME)`.

### `re`

This target depends on `fclean` and then `all`, effectively recompiling everything from scratch.

### `rebonus`

This target depends on `fclean` and then `bonus`, recompiling everything from scratch and including the bonus files.

## Makefile Code

```makefile
LIB = ar
RM = rm -f

CC = gcc
CCFLAGS = -Wall -Wextra -Werror

NAME = libft.a
SRC = ft_strlen.c ft_isalpha.c ft_isalnum.c ft_isascii.c ft_isdigit.c\
ft_isprint.c ft_toupper.c ft_tolower.c ft_strlcpy.c ft_strlcat.c ft_strncmp.c\
ft_strnstr.c ft_atoi.c ft_strchr.c ft_strrchr.c ft_memset.c ft_bzero.c ft_memcpy.c\
ft_memmove.c ft_memchr.c ft_memcmp.c ft_calloc.c ft_strdup.c ft_substr.c\
ft_strjoin.c ft_strtrim.c ft_split.c ft_itoa.c ft_strmapi.c ft_striteri.c\
ft_putchar_fd.c ft_putstr_fd.c ft_putendl_fd.c ft_putnbr_fd.c
OBJ = $(SRC:.c=.o)
INCLUDE = libft.h

BONUS_SRC = ft_lstnew_bonus.c ft_lstadd_front_bonus.c ft_lstsize_bonus.c ft_lstlast_bonus.c\
ft_lstadd_back_bonus.c ft_lstdelone_bonus.c ft_lstclear_bonus.c ft_lstiter_bonus.c ft_lstmap_bonus.c
BONUS_OBJ = $(BONUS_SRC:.c=.o)

.PHONY: all clean fclean re bonus

all: $(NAME)

$(NAME): $(OBJ)
	$(LIB) rcs $(NAME) $(OBJ)

bonus: $(OBJ) $(BONUS_OBJ)
	$(LIB) r $(NAME) $(BONUS_OBJ)

%.o: %.c $(INCLUDE)
	$(CC) $(CCFLAGS) -c -o $@ $<

clean:
	$(RM) $(OBJ) $(BONUS_OBJ)

fclean: clean
	$(RM) $(NAME)

re: fclean all

rebonus: fclean bonus
