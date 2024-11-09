| **Function Declaration**                           | A named function that can be called later. Defined with the `function` keyword.          | `function greet() { console.log("Hello, World!"); }`                     |
| -------------------------------------------------- | ---------------------------------------------------------------------------------------- | ------------------------------------------------------------------------ |
| **Function Expression**                            | A function that is assigned to a variable. Can be anonymous or named.                    | `const greet = function() { console.log("Hello, World!"); };`            |
| **Arrow Function**                                 | A shorthand syntax for writing functions. It doesn't have its own `this` value.          | `const greet = () => { console.log("Hello, World!"); };`                 |
| **Anonymous Function**                             | A function without a name. Often used in callbacks or as function expressions.           | `setTimeout(function() { console.log("Hello after 1 second"); }, 1000);` |
| Function Type                                      | Description                                                                              | Syntax Example                                                           |
| **IIFE (Immediately Invoked Function Expression)** | A function that runs as soon as it’s defined. Typically wrapped in parentheses.          | `(function() { console.log("This runs immediately!"); })();`             |
| **Function Constructor**                           | A function that is created dynamically using the `Function` constructor.                 | `const greet = new Function('console.log("Hello, World!");');`           |
| **Generator Function**                             | A function that can be paused and resumed using `yield` keyword. It returns an iterator. | `function* greet() { yield "Hello"; yield "World"; }`                    |
```js
// Function Declaration
function greet() {
  console.log("Hello, World!");
}

// Function Expression
const greetExpression = function() {
  console.log("Hello, World!");
};

// Arrow Function
const greetArrow = () => {
  console.log("Hello, World!");
};

// Anonymous Function
setTimeout(function() {
  console.log("Hello after 1 second");
}, 1000);

// IIFE (Immediately Invoked Function Expression).
(function() {
  console.log("This runs immediately!");
})();

// Function Constructor

const greetConstructor = new Function('console.log("Hello, World!");');

// Generator Function

function* greetGenerator() {
  yield "Hello";
  yield "World";
}
```