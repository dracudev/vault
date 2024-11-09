| Method/Operation        | Description                                                                                                  | Syntax Example                             |
| ----------------------- | ------------------------------------------------------------------------------------------------------------ | ------------------------------------------ |
| Object.create()         | Creates a new object, using an existing object as the prototype of the newly created object.                 | `let obj = Object.create(protoObj);`       |
| Object.assign()         | Copies all enumerable own properties from one or more source objects to a target object.                     | `Object.assign(target, source1, source2);` |
| Object.keys()           | Returns an array of a given object's own enumerable property names.                                          | `let keys = Object.keys(obj);`             |
| Object.values()         | Returns an array of a given object's own enumerable property values.                                         | `let values = Object.values(obj);`         |
| Object.entries()        | Returns an array of a given object's own enumerable string-keyed property `[key, value]` pairs.              | `let entries = Object.entries(obj);`       |
| Object.freeze()         | Freezes an object, making it immutable (cannot add, remove, or modify properties).                           | `Object.freeze(obj);`                      |
| Object.seal()           | Seals an object, preventing new properties from being added but allows modifications to existing properties. | `Object.seal(obj);`                        |
| Object.hasOwn()         | Checks if an object has a specific property as its own property (not inherited).                             | `obj.hasOwnProperty("key");`               |
| Object.getPrototypeOf() | Returns the prototype (internal [[Prototype]]) of an object.                                                 | `let proto = Object.getPrototypeOf(obj);`  |
| Object.setPrototypeOf() | Sets the prototype (internal [[Prototype]]) of an object.                                                    | `Object.setPrototypeOf(obj, newProto);`    |
```js
// Object.create()
let protoObj = { greet: function() { console.log("Hello!"); } };
let obj = Object.create(protoObj);
obj.greet();  // "Hello!"

// Object.assign()
let target = { a: 1 };
let source1 = { b: 2 };
let source2 = { c: 3 };
Object.assign(target, source1, source2);  // target = { a: 1, b: 2, c: 3 }
console.log(target);

// Object.keys()
let obj = { name: "John", age: 30 };
let keys = Object.keys(obj);  // ["name", "age"]
console.log(keys);

// Object.values()
let obj = { name: "John", age: 30 };
let values = Object.values(obj);  // ["John", 30]
console.log(values);

// Object.entries()
let obj = { name: "John", age: 30 };
let entries = Object.entries(obj);  // [["name", "John"], ["age", 30]]
console.log(entries);

// Object.freeze()
let obj = { name: "John", age: 30 };
Object.freeze(obj);
obj.age = 35;  // Won't work, obj is immutable
console.log(obj.age);  // 30

// Object.seal()
let obj = { name: "John", age: 30 };
Object.seal(obj);
obj.age = 35;  // Works, existing properties can be modified
obj.city = "New York";  // Won't work, new properties can't be added
console.log(obj);

// Object.hasOwn()
let obj = { name: "John", age: 30 };
console.log(obj.hasOwnProperty("name"));  // true
console.log(obj.hasOwnProperty("city"));  // false

// Object.getPrototypeOf()
let obj = {};
let proto = Object.getPrototypeOf(obj);  // proto is the prototype of the object
console.log(proto);  // [Object: null prototype] {}

// Object.setPrototypeOf()
let obj = {};
let newProto = { greet: function() { console.log("Hello!"); } };
Object.setPrototypeOf(obj, newProto);
obj.greet();  // "Hello!"

```