ASCII (American Standard Code for Information Interchange) is a character encoding standard originally developed in the early 1960s for representing text in computers and communications equipment. It defines numeric codes (0-127) for various characters, including letters, digits, punctuation marks, and control characters, allowing computers to exchange and display textual information consistently.

### ASCII Basics

1. **Character Set**: ASCII defines codes for 128 characters, where each character is represented by a 7-bit binary number (0 to 127). This includes:
    
    - Printable characters (letters, digits, punctuation): 'A' to 'Z' (65-90), 'a' to 'z' (97-122), '0' to '9' (48-57), and symbols like '@', '#', '$', etc.
    - Non-printable control characters: Such as newline (LF), carriage return (CR), tab (TAB), etc.
2. **Extended ASCII**: In addition to the standard 7-bit ASCII, extended ASCII uses the eighth bit (128-255) to represent additional characters specific to different languages and graphical symbols. However, extended ASCII varies between different systems and is not universally standardized.
### ASCII Table Examples

Here are some examples of ASCII characters and their corresponding decimal values:

- **Printable Characters**:
    
    - `'A'` - Decimal: 65
    - `'Z'` - Decimal: 90
    - `'a'` - Decimal: 97
    - `'z'` - Decimal: 122
    - `'0'` - Decimal: 48
    - `'9'` - Decimal: 57
- **Non-Printable Control Characters**:
    
    - `'\n'` (Newline) - Decimal: 10
    - `'\r'` (Carriage return) - Decimal: 13
    - `'\t'` (Tab) - Decimal: 9
    - `'\0'` (Null) - Decimal: 0
    - `'\b'` (Backspace) - Decimal: 8

### Using ASCII in C Programming

In C programming, ASCII characters can be represented using their decimal values and can be manipulated using character literals and functions from the standard library (`<ctype.h>`).
```c
int num = 'A';  // num will be assigned the ASCII value of 'A' (65)
```

In C, adding `48` or `'0'` to an `int` converts the integer value into its corresponding ASCII character representation. This is because in the ASCII encoding scheme, the decimal digits '0' to '9' have consecutive values from 48 to 57.
```c
int num = 5;
char ch = num + 48;  // Converts '5' (integer) to '5' (character)

printf("Character representation: %c\n", ch);  // Output: '5'
```