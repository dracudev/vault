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
#include <stdio.h>

// Function to convert integer to hexadecimal and print it
void decimalToHexadecimal(int num) {
    // Array to store hexadecimal digits
    char hex[100];
    int i = 0;

    // Handling special case for 0
    if (num == 0) {
        printf("Hexadecimal: 0\n");
        return;
    }

    // Process each digit
    while (num != 0) {
        int remainder = num % 16;
        if (remainder < 10)
            hex[i++] = remainder + '0';
        else
            hex[i++] = remainder + 'A' - 10;
        num = num / 16;
    }

    // Print hexadecimal in reverse order
    printf("Hexadecimal: ");
    for (int j = i - 1; j >= 0; j--)
        printf("%c", hex[j]);
    printf("\n");
}

int main() {
    int number = 2348;
    decimalToHexadecimal(number);
    return 0;
}
```

### Explanation

- **Function `decimalToHexadecimal`**:
    - Accepts an integer (`num`) and converts it into its hexadecimal representation.
    - Uses `%` to get remainders which are then mapped to hexadecimal digits.
    - Divides the number by 16 until it becomes zero.
    - Outputs the hexadecimal digits in reverse order to get the correct representation.