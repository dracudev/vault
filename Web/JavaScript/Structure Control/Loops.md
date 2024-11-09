
| Loop Type    | Description                                                                                                | Syntax Example                                                                        |
| ------------ | ---------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------- |
| `for`        | Iterates a specific number of times. It has an initialization, condition, and update expression.           | `for (let i = 0; i < 5; i++) { console.log(i); }`                                     |
| `while`      | Executes a block of code as long as a condition is true. The condition is checked before each iteration.   | `let i = 0; while (i < 5) { console.log(i); i++; }`                                   |
| `do...while` | Similar to `while`, but executes the code block at least once before checking the condition.               | `let i = 0; do { console.log(i); i++; } while (i < 5);`                               |
| `for...of`   | Iterates over the values of iterable objects (like arrays, strings, maps, etc.).                           | `let arr = [1, 2, 3]; for (let value of arr) { console.log(value); }`                 |
| `for...in`   | Iterates over the enumerable properties of an object (including keys).                                     | `let obj = {a: 1, b: 2}; for (let key in obj) { console.log(key, obj[key]); }`        |
| `.forEach()` | Array method that executes a function for each element. It does not return anything and cannot be stopped. | `let arr = [1, 2, 3]; arr.forEach((value) => { console.log(value); });`               |
| `.map()`     | Array method that creates a new array with the results of calling a function on every element.             | `let arr = [1, 2, 3]; let newArr = arr.map(value => value * 2); console.log(newArr);` |
```js
// for loop
for (let i = 0; i < 5; i++) {
  console.log("For loop iteration: " + i);
}

// while loop
let i = 0;
while (i < 5) {
  console.log("While loop iteration: " + i);
  i++;
}

// do...while loop.
let j = 0;
do {
  console.log("Do-while loop iteration: " + j);
  j++;
} while (j < 5);

// for...in loop
let person = { name: "John", age: 30, city: "New York" };
for (let key in person) {
  console.log(key + ": " + person[key]);
}

// for...of loop
let arr = [10, 20, 30, 40];
for (let value of arr) {
  console.log("For-of loop value: " + value);
}

```