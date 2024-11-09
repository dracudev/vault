
| Operator   | Description                                                                                             | Syntax Example                                                                                                           |
|------------|---------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------|
| `Rest`     | Collects all remaining elements in an array or object into a single variable.                           | `function sum(...numbers) { return numbers.reduce((a, b) => a + b, 0); }`                                             |
| `Spread`   | Expands an iterable (like an array or object) into individual elements or properties.                    | `let arr = [...array1, ...array2];`                                                                                      |
| `Rest (Object)` | Collects remaining properties of an object into a new object.                                          | `let {a, b, ...rest} = obj;`                                                                                             |
| `Spread (Object)` | Copies properties from one object into another object.                                                 | `let newObj = { ...obj1, ...obj2 };`                                                                                     |
```js
// Rest Operator (Array)
function sum(...numbers) {
  return numbers.reduce((a, b) => a + b, 0);  // Sum all numbers
}
console.log(sum(1, 2, 3, 4));  // 10

// Spread Operator (Array)
let array1 = [1, 2];
let array2 = [3, 4];
let combined = [...array1, ...array2];  // [1, 2, 3, 4]
console.log(combined);

// Rest Operator (Object)
let obj = { a: 1, b: 2, c: 3, d: 4 };
let { a, b, ...rest } = obj;  // rest = { c: 3, d: 4 }
console.log(rest);

// Spread Operator (Object)
let obj1 = { a: 1, b: 2 };
let obj2 = { c: 3, d: 4 };
let mergedObj = { ...obj1, ...obj2 };  // { a: 1, b: 2, c: 3, d: 4 }
console.log(mergedObj);

```