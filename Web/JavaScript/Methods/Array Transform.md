| Method     | Description                                                                                                                  | Syntax Example                                           |
| ---------- | ---------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------- |
| `map()`    | Creates a new array populated with the results of calling a provided function on every element in the array.                 | `let result = arr.map(x => x * 2);`                      |
| `filter()` | Creates a new array with all elements that pass the test implemented by the provided function.                               | `let result = arr.filter(x => x > 5);`                   |
| `find()`   | Returns the first element in the array that satisfies the provided testing function. If none found, returns `undefined`.     | `let result = arr.find(x => x > 5);`                     |
| `reduce()` | Applies a function against an accumulator and each element in the array (from left to right) to reduce it to a single value. | `let result = arr.reduce((acc, curr) => acc + curr, 0);` |
| `sort()`   | Sorts the elements of an array in place and returns the sorted array.                                                        | `let result = arr.sort((a, b) => a - b);`                |
| `some()`   | Tests whether at least one element in the array passes the provided testing function.                                        | `let result = arr.some(x => x > 5);`                     |
| `every()`  | Tests whether all elements in the array pass the provided testing function.                                                  | `let result = arr.every(x => x > 5);`                    |
| `push()`   | Adds one or more elements to the end of an array and returns the new array length.                                           | `arr.push(5);`                                           |
| `pop()`    | Removes the last element from an array and returns that element.                                                             | `let last = arr.pop();`                                  |
| `splice()` | Changes the contents of an array by removing or replacing existing elements and/or adding new ones.                          | `arr.splice(2, 1, "new");`                               |
| `slice()`  | Returns a shallow copy of a portion of an array into a new array object. Does not modify the original array.                 | `let newArr = arr.slice(1, 4);`                          |
```js
// map()
let arr = [1, 2, 3, 4];
let result = arr.map(x => x * 2);  // [2, 4, 6, 8]

// filter()
let arr = [1, 2, 3, 4, 5, 6];
let result = arr.filter(x => x > 5);  // [6]

// find()
let arr = [1, 2, 3, 4, 5];
let result = arr.find(x => x > 3);  // 4

// reduce()
let arr = [1, 2, 3, 4];
let result = arr.reduce((acc, curr) => acc + curr, 0);  // 10

// sort()
let arr = [5, 3, 8, 1];
let result = arr.sort((a, b) => a - b);  // [1, 3, 5, 8]

// some()
let arr = [1, 2, 3, 4, 5];
let result = arr.some(x => x > 5);  // false

// every()
let arr = [1, 2, 3, 4, 5];
let result = arr.every(x => x > 0);  // true

// push()
let arr = [1, 2, 3];
arr.push(5);  // arr becomes [1, 2, 3, 5]

// pop()
let arr = [1, 2, 3];
let last = arr.pop();  // last = 3, arr becomes [1, 2]

// splice()
let arr = [1, 2, 3, 4];
arr.splice(2, 1, "new");  // arr becomes [1, 2, "new", 4]

// slice()
let arr = [1, 2, 3, 4];
let newArr = arr.slice(1, 4);  // newArr becomes [2, 3, 4]

```