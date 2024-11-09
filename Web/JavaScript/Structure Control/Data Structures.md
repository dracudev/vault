
| Data Structure       | Description                                                                                                      | Syntax Example                                                                                      |
|----------------------|------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------|
| **Array**            | An ordered collection of values, indexed by integers. Can store multiple values of any type.                     | `let arr = [1, 2, 3, 4];`                                                                            |
| **Object**           | A collection of key-value pairs. Keys are strings (or symbols) and values can be any type.                      | `let obj = { name: "John", age: 30 };`                                                               |
| **Set**              | A collection of unique values (no duplicates). Can store any type of values, but each value can only occur once. | `let mySet = new Set([1, 2, 3, 3, 4]);`                                                              |
| **Map**              | A collection of key-value pairs, where keys can be of any type (not just strings).                              | `let map = new Map([["key1", "value1"], ["key2", "value2"]]);`                                       |
| **WeakSet**          | A collection of unique values, but unlike `Set`, it only holds **weak references** to objects.                  | `let weakSet = new WeakSet([obj1, obj2]);`                                                           |
| **WeakMap**          | A collection of key-value pairs where keys are objects and values can be any type. WeakMap only holds **weak references** to keys. | `let weakMap = new WeakMap([[obj, "value"]]);`                                                        |
| **TypedArray**       | Represents an array-like view of binary data. Includes various types like `Int8Array`, `Float32Array`, etc.      | `let typedArray = new Int16Array([1, 2, 3]);`                                                       |
```js
// Array
let arr = [1, 2, 3, 4];

// Object
let obj = { name: "John", age: 30 };

// Set
let mySet = new Set([1, 2, 3, 3, 4]);

// Map
let map = new Map([["key1", "value1"], ["key2", "value2"]]);

// WeakSet
let weakSet = new WeakSet([obj1, obj2]);

// WeakMap
let weakMap = new WeakMap([[obj, "value"]]);

// TypedArray
let typedArray = new Int16Array([1, 2, 3]);
```