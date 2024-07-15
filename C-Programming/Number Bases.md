### 1. Decimal (Base 10)

- **Description**: Decimal is the most common base used by humans, with digits ranging from 0 to 9.
- **Example**: `123` represents one hundred twenty-three in decimal.

### 2. Binary (Base 2)

- **Description**: Binary uses only two digits: 0 and 1.
- **Example**: `101` represents five in decimal (`1*2^2 + 0*2^1 + 1*2^0`).

### 3. Octal (Base 8)

- **Description**: Octal uses digits from 0 to 7.
- **Example**: `53` in octal represents forty-three in decimal (`5*8^1 + 3*8^0`).

### 4. Hexadecimal (Base 16)

- **Description**: Hexadecimal uses digits from 0 to 9 and letters A to F (or a to f) to represent values from 10 to 15.
- **Example**: `1A` in hexadecimal represents twenty-six in decimal (`1*16^1 + 10*16^0`).

## Creating a Hexadecimal Function in C

### Purpose

To convert a given integer into its hexadecimal representation.

### Implementation Steps

1. **Understand the Conversion**: Hexadecimal representation converts a number into base 16. Each digit can represent values from 0 to 15, where A-F correspond to 10-15.
    
2. **Algorithm**:
    
    - Initialize an array to store hexadecimal digits.
    - Use modulo (`%`) operation to extract remainders, which are the hexadecimal digits.
    - Divide the number by 16 iteratively until it becomes zero.
    - Reverse the array to get the correct hexadecimal representation.

### Example Function

Here's a simple implementation of a hexadecimal conversion function in C:
```c
void ft_hexadecimal(unsigned int x)
{
    char str[25];  // Buffer to store the hexadecimal digits
    char *base;    // Pointer to the character set for hexadecimal conversion
    int i;         // Index variable for iterating through str array

    base = "0123456789ABCDEF";
    i = 0;  // Initialize index variable

    // Handle special case when x is 0
    if (x == 0)
    {
        ft_putchar('0');  // Output '0'
        return;           // Exit the function
    }

    // Convert x to hexadecimal and store in the str array
    while (x != 0)
    {
        str[i] = base[x % 16];  // Convert remainder of x divided by 16 to hexadecimal digit
        x = x / 16;             // Divide x by 16 to shift to the next hexadecimal digit
        i++;                    // Move to the next position in the str array
    }

    // Output the hexadecimal digits stored in str array in reverse order
    while (i--)
        ft_putchar(str[i]);  // Output each character of str in reverse order
}

```

### Explanation

- **Initialization**:
    
    - `str[25]`: This array (`str`) is used to store the hexadecimal digits temporarily. It has a size of 25, which is enough to store a 32-bit unsigned integer in hexadecimal (including the terminating null character).
    - `base`: This pointer points to a character array that contains the hexadecimal digits.
    - `i`: This integer variable is used as an index to keep track of where to store characters in the `str` array.
- **Handling the Special Case (x == 0)**:
    
    - If `x` is equal to 0, it simply outputs `'0'` using the `ft_putchar` function and returns from the function early.
- **Converting to Hexadecimal**:
    
    - The function enters a `while` loop that continues until `x` becomes 0.
    - Inside the loop:
        - `str[i] = base[x % 16];`: Computes the remainder of `x` divided by 16 (`x % 16`) and uses it as an index into the `base` array to fetch the corresponding hexadecimal digit. This digit is then stored in the `str` array at position `i`.
        - `x = x / 16;`: Updates `x` by integer division with 16 (`x / 16`), effectively shifting `x` right by one hexadecimal digit.
        - `i++;`: Increments `i` to move to the next position in the `str` array for the next hexadecimal digit.
- **Outputting the Hexadecimal Representation**:
    
    - After the `while` loop completes, `i` now holds the number of digits in the hexadecimal representation minus one.
    - The function then enters another `while` loop where it outputs each character stored in `str` in reverse order (`str[i]`) using `ft_putchar`.
    - This effectively prints the hexadecimal number stored in `str` in the correct order.
- **Example**
	- Let's say `x = 26` (decimal), which is `1A` in hexadecimal.
	- During conversion:
	    - `base[26 % 16]` gives remainder `10` which in the base array is `'A'`, so `str[0]` is `'A'`.
	    - `x = 26 / 16` gives `1`, so `base[1 % 16]` gives `'1'`, so `str[1]` is `'1'`.
	    - `x = 1 / 16` gives `0`, so conversion stops.
	- `str` now contains `'1'` in `str[1]` and `'A'` in `str[0]`.
	- The result is printed in reverse order.