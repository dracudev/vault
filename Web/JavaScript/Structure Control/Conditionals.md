
| Conditional Type        | Description                                                                                          | Syntax Example                                                                                                          |
| ----------------------- | ---------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------- |
| `if`                    | Executes a block of code if a specified condition is true.                                           | `if (condition) { console.log("Condition is true"); }`                                                                  |
| `else`                  | Executes a block of code if the condition in the `if` statement is false.                            | `if (condition) { console.log("Condition is true"); } else { console.log("Condition is false"); }`                      |
| `else if`               | Specifies a new condition to test if the previous `if` condition is false.                           | `if (condition1) { console.log("Condition 1 is true"); } else if (condition2) { console.log("Condition 2 is true"); }`  |
| `switch`                | Evaluates an expression and executes corresponding case blocks based on the value of the expression. | `switch (expression) { case value1: console.log("Value is 1"); break; case value2: console.log("Value is 2"); break; }` |
| `ternary (conditional)` | A shorthand for an `if-else` statement, returns one of two values based on the condition.            | `let result = condition ? "True" : "False";`                                                                            |
```js
// if statement
if (condition) {
  console.log("Condition is true");
}

// else statement
if (condition) {
  console.log("Condition is true");
} else {
  console.log("Condition is false");
}

// else if statement
if (condition1) {
  console.log("Condition 1 is true");
} else if (condition2) {
  console.log("Condition 2 is true");
}

// switch statement
let expression = "apple";
switch (expression) {
  case "apple":
    console.log("This is an apple");
    break;
  case "banana":
    console.log("This is a banana");
    break;
  default:
    console.log("Unknown fruit");
}

// ternary (conditional) operator
let result = condition ? "True" : "False";
console.log(result);

```