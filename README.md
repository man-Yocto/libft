# libft

[![CI](https://github.com/man-Yocto/libft/actions/workflows/ci.yml/badge.svg)](https://github.com/man-Yocto/libft/actions/workflows/ci.yml)

My own C standard library, written from scratch as the first project of the 42 curriculum.
It reimplements a subset of libc plus extra string, output, and linked-list helpers, and is
reused across my later 42 projects (pipex, push_swap, minishell, cub3D, …).

Everything compiles with `-Wall -Wextra -Werror` and follows the 42 Norm.

## Build

```bash
make          # builds libft.a (mandatory part)
make bonus    # adds the linked-list functions
make clean    # removes object files
make fclean   # removes object files and libft.a
make re       # full rebuild
```

Use it in a project:

```bash
cc -Wall -Wextra -Werror main.c -I path/to/libft -L path/to/libft -lft
```

## Functions

### Character checks & conversion (`<ctype.h>`)
| Function | Description |
|---|---|
| `ft_isalpha` | Alphabetic character? |
| `ft_isdigit` | Decimal digit? |
| `ft_isalnum` | Alphanumeric character? |
| `ft_isascii` | 7-bit ASCII value? |
| `ft_isprint` | Printable character (including space)? |
| `ft_toupper` | Convert to uppercase |
| `ft_tolower` | Convert to lowercase |

### Memory (`<string.h>` / `<stdlib.h>`)
| Function | Description |
|---|---|
| `ft_memset` | Fill memory with a byte |
| `ft_bzero` | Zero a memory area |
| `ft_memcpy` | Copy memory (non-overlapping) |
| `ft_memmove` | Copy memory (overlap-safe) |
| `ft_memchr` | Find a byte in memory |
| `ft_memcmp` | Compare two memory areas |
| `ft_calloc` | Allocate zero-initialised memory |

### Strings (`<string.h>` / `<stdlib.h>`)
| Function | Description |
|---|---|
| `ft_strlen` | String length |
| `ft_strlcpy` | Size-bounded string copy |
| `ft_strlcat` | Size-bounded string concatenation |
| `ft_strchr` | First occurrence of a character |
| `ft_strrchr` | Last occurrence of a character |
| `ft_strncmp` | Compare up to *n* characters |
| `ft_strnstr` | Find a substring within *n* characters |
| `ft_strdup` | Duplicate a string |
| `ft_atoi` | String to `int` |

### Additional string utilities
| Function | Description |
|---|---|
| `ft_substr` | Extract a substring |
| `ft_strjoin` | Concatenate two strings into a new one |
| `ft_strtrim` | Trim a set of characters from both ends |
| `ft_split` | Split a string by a delimiter into an array |
| `ft_itoa` | `int` to string |
| `ft_strmapi` | Map a function over a string (new string) |
| `ft_striteri` | Apply a function to each character in place |

### Output to file descriptors
| Function | Description |
|---|---|
| `ft_putchar_fd` | Write a character |
| `ft_putstr_fd` | Write a string |
| `ft_putendl_fd` | Write a string followed by a newline |
| `ft_putnbr_fd` | Write an integer |

### Linked lists (bonus)
Operates on `t_list { void *content; struct s_list *next; }`.

| Function | Description |
|---|---|
| `ft_lstnew` | Create a node |
| `ft_lstadd_front` | Add a node at the front |
| `ft_lstadd_back` | Add a node at the end |
| `ft_lstsize` | Count nodes |
| `ft_lstlast` | Get the last node |
| `ft_lstdelone` | Free one node's content and the node |
| `ft_lstclear` | Free a whole list |
| `ft_lstiter` | Apply a function to each node's content |
| `ft_lstmap` | Build a new list by mapping a function |

## History

Extracted from [`pipex/includes/libft`](https://github.com/man-Yocto/pipex) with
`git subtree split`, so the original commit history is preserved.
