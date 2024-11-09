| Loop Type               | Description                                                                                                  | Syntax Example                                                               |
| ----------------------- | ------------------------------------------------------------------------------------------------------------ | ---------------------------------------------------------------------------- |
| `forEach`               | Executes a provided function once for each array element.                                                    | `arr.forEach(element => { console.log(element); });`                         |
| `for...of`              | Iterates over the values of an iterable object (like an array).                                              | `for (let value of arr) { console.log(value); }`                             |
| `for...in`              | Iterates over the keys (indices) of an object or array.                                                      | `for (let index in arr) { console.log(index); }`                             |
| `for...of (with break)` | Iterates over the values of an iterable object and allows breaking out of the loop with a `break` statement. | `for (let value of arr) { if (value === 3) { break; } console.log(value); }` |
| `for...of (with index)` | Iterates over the values of an iterable object and includes an index to track the position of elements.      | `let index = 0; for (let value of arr) { console.log(index++, value); }`     |
```js
// forEach loop
let arr = [1, 2, 3, 4];
arr.forEach(element => {
  console.log(element);
});

// for...of loop
for (let value of arr) {
  console.log(value);
}

// for...in loop
for (let index in arr) {
  console.log(index);
}

// for...of loop with break
for (let value of arr) {
  if (value === 3) {
    break;
  }
  console.log(value);
}

// for...of loop with index
let index = 0;
for (let value of arr) {
  console.log(index++, value);
}
```