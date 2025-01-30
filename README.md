# Introduction

This document describes the implementation of the `string.h` library in the C programming language, including the implementation of the `sprintf` and `sscanf` functions. The `string.h` library is the core library in C for string manipulation.

## Functions in string.h

| №  | Function                                   | Description                                                                                                                                              |
|----|-------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1  | `void *memchr(const void *str, int c, size_t n)`  | Searches for the first occurrence of the character `c` (unsigned type) in the first `n` bytes of the string pointed to by `str`.                        |
| 2  | `int memcmp(const void *str1, const void *str2, size_t n)` | Compares the first `n` bytes of the strings `str1` and `str2`.                                                                                         |
| 3  | `void *memcpy(void *dest, const void *src, size_t n)` | Copies `n` bytes from `src` to `dest`. Does not check for overlapping memory areas.                                                                     |
| 4  | `void *memset(void *str, int c, size_t n)`      | Copies the character `c` (unsigned type) into the first `n` bytes of the string pointed to by `str`.                                                   |
| 5  | `char *strncat(char *dest, const char *src, size_t n)` | Appends the string `src` to the end of the string `dest`, up to `n` characters.                                                                          |
| 6  | `char *strchr(const char *str, int c)`       | Searches for the first occurrence of the character `c` (unsigned type) in the string `str`.                                                              |
| 7  | `int strncmp(const char *str1, const char *str2, size_t n)` | Compares at most the first `n` bytes of the strings `str1` and `str2`.                                                                                 |
| 8  | `char *strncpy(char *dest, const char *src, size_t n)` | Copies up to `n` characters from the string `src` to `dest`. If `src` is shorter than `n`, `dest` is padded with null characters.                      |
| 9  | `size_t strcspn(const char *str1, const char *str2)` | Calculates the length of the initial segment of `str1` which consists entirely of characters not in `str2`.                                             |
| 10 | `char *strerror(int errnum)`                | Searches for the error message corresponding to the error number `errnum` and returns a pointer to the message string.                                  |
| 11 | `size_t strlen(const char *str)`           | Computes the length of the string `str`, excluding the terminating null character.                                                                       |
| 12 | `char *strpbrk(const char *str1, const char *str2)` | Finds the first character in `str1` that matches any character in `str2`.                                                                                |
| 13 | `char *strrchr(const char *str, int c)`    | Searches for the last occurrence of the character `c` (unsigned type) in the string `str`.                                                               |
| 14 | `char *strstr(const char *haystack, const char *needle)` | Finds the first occurrence of the string `needle` in the string `haystack`.                                                                             |
| 15 | `char *strtok(char *str, const char *delim)` | Breaks the string `str` into tokens separated by `delim`. Initially, a pointer to the string is passed, with subsequent calls passing `NULL`.         |

## Function `sprintf`

- The `sprintf` function has been implemented to format a string according to a specified format.
- Supported format specifiers include:
  - `c` - character;
  - `d` - decimal integer;
  - `f` - floating-point number;
  - `s` - string;
  - `u` - unsigned integer;
  - `%` - percent sign.
- Formatting flags are implemented:
  - `-` - left-align the output;
  - `+` - show the sign for numbers;
  - space - add a space before positive numbers.
- Field width and precision formatting can be specified by either a number or a dot:
  - Width: `(number)`;
  - Precision: `.(number)`.
- Length modifiers:
  - `h` - for short integers;
  - `l` - for long integers.

## Function `sscanf`

- The `sscanf` function has been implemented to read formatted data from a string.
- Full formatting is supported, taking into account flags, width, precision, modifiers, and conversion types.
- The function allows extraction of data from a string into specified variables based on the provided format.

## Additional String Processing Functions

- Functions for string processing, inspired by the `String` class in C++, have been implemented.
- The functions meet the requirements for string manipulation, allowing for more flexible management of string data and various operations.
