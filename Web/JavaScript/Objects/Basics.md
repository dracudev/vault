| Concept              | Description                                                              | Syntax Example                                                                                     |
| -------------------- | ------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------- |
| Object Creation      | Creates a new object using `{}` or `new Object()`.                       | `let obj = {};`                                                                                    |
| Property Access      | Accesses or assigns properties using dot notation or bracket notation.   | `obj.name = "John";` or `obj["name"] = "John";`                                                    |
| Object Methods       | Functions that belong to an object, defined as properties.               | `let obj = { greet: function() { console.log("Hello!"); } }; obj.greet();`                         |
| `this` Keyword       | Refers to the object itself inside a method.                             | `let obj = { name: "John", greet: function() { console.log(this.name); } }; obj.greet();`          |
| Object Destructuring | A convenient way to extract values from objects into variables.          | `let { name, age } = obj;`                                                                         |
| Object Constructor   | A function used to create objects, allowing object creation using `new`. | `function Person(name, age) { this.name = name; this.age = age; } let p = new Person("John", 30);` |
```js
// Object Creation
let obj = {};  // Creates an empty object

// Property Access (dot notation)
obj.name = "John";  // Adding property to the object
console.log(obj.name);  // "John"

// Property Access (bracket notation)
obj["age"] = 30;
console.log(obj["age"]);  // 30

// Object Methods
let obj = {
  greet: function() {
    console.log("Hello!");
  }
};
obj.greet();  // "Hello!"

// `this` Keyword
let obj = {
  name: "John",
  greet: function() {
    console.log(this.name);
  }
};
obj.greet();  // "John"

// Object Destructuring
let obj = { name: "John", age: 30 };
let { name, age } = obj;
console.log(name, age);  // "John", 30

// Object Constructor
function Person(name, age) {
  this.name = name;
  this.age = age;
}
let p = new Person("John", 30);
console.log(p.name, p.age);  // "John", 30
```