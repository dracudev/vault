| Method          | Description                                                                                           | Syntax Example                                 |
| --------------- | ----------------------------------------------------------------------------------------------------- | ---------------------------------------------- |
| `charAt()`      | Returns the character at a specified index in a string.                                               | `let char = str.charAt(0);`                    |
| `concat()`      | Combines two or more strings and returns a new string.                                                | `let result = str1.concat(" ", str2);`         |
| `includes()`    | Checks if a string contains a specified substring.                                                    | `let result = str.includes("apple");`          |
| `indexOf()`     | Returns the index of the first occurrence of a specified value in a string. If not found, returns -1. | `let index = str.indexOf("apple");`            |
| `replace()`     | Replaces a specified substring with a new substring in a string.                                      | `let newStr = str.replace("apple", "banana");` |
| `slice()`       | Extracts a part of a string and returns a new string without modifying the original string.           | `let part = str.slice(1, 4);`                  |
| `split()`       | Splits a string into an array of substrings based on a specified separator.                           | `let arr = str.split(" ");`                    |
| `toLowerCase()` | Converts all the characters in a string to lowercase.                                                 | `let lowerStr = str.toLowerCase();`            |
| `toUpperCase()` | Converts all the characters in a string to uppercase.                                                 | `let upperStr = str.toUpperCase();`            |
| `trim()`        | Removes whitespace from both ends of a string.                                                        | `let trimmed = str.trim();`                    |
```js
// charAt()
let str = "Hello";
let char = str.charAt(0);  // "H"

// concat()
let str1 = "Hello";
let str2 = "World";
let result = str1.concat(" ", str2);  // "Hello World"

// includes()
let str = "Hello World";
let result = str.includes("apple");  // false

// indexOf()
let str = "Hello World";
let index = str.indexOf("apple");  // -1

// replace()
let str = "I have an apple";
let newStr = str.replace("apple", "banana");  // "I have a banana"

// slice()
let str = "Hello World";
let part = str.slice(1, 4);  // "ell"

// split()
let str = "Hello World";
let arr = str.split(" ");  // ["Hello", "World"]

// toLowerCase()
let str = "Hello";
let lowerStr = str.toLowerCase();  // "hello"

// toUpperCase()
let str = "Hello";
let upperStr = str.toUpperCase();  // "HELLO"

// trim()
let str = "  Hello World  ";
let trimmed = str.trim();  // "Hello World"

```