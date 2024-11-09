| Concept              | Description                                                              | Syntax Example                                                                      |
| -------------------- | ------------------------------------------------------------------------ | ----------------------------------------------------------------------------------- |
| Variable Declaration | Declares variables using `let`, `const`, or `var` with type annotations. | `let num: number = 5;`                                                              |
| Type Inference       | TypeScript automatically infers the type when not explicitly specified.  | `let num = 5;`  // Type inferred as number                                          |
| Functions with Types | Declares function parameters and return types.                           | `function add(a: number, b: number): number { return a + b; }`                      |
| Interfaces           | Defines custom types for objects or classes.                             | `interface Person { name: string; age: number; }`                                   |
| Classes              | Defines a class with types for properties and methods.                   | `class Person { name: string; constructor(name: string) { this.name = name; } }`    |
| Type Aliases         | Creates custom type names using `type`.                                  | `type StringOrNumber = string \| number;                                            |
| Arrays               | Declares arrays with specific types for the elements.                    | `let numbers: number[] = [1, 2, 3];`                                                |
| Tuples               | Creates arrays with fixed types at specific positions.                   | `let person: [string, number] = ["John", 30];`                                      |
| Enums                | Defines a set of named constants.                                        | `enum Color { Red, Green, Blue }`                                                   |
| Type Assertions      | Tells TypeScript to treat a value as a specific type.                    | `let someValue: any = "hello"; let strLength: number = (<string>someValue).length;` |
| Any Type             | Allows any type for a variable when unsure about the type.               | `let data: any = 42;`                                                               |
```ts
// Variable Declaration
let num: number = 5;

// Type Inference
let num = 5;  // Type inferred as number

// Functions with Types
function add(a: number, b: number): number {
  return a + b;
}

// Interfaces
interface Person {
  name: string;
  age: number;
}
let person: Person = { name: "John", age: 30 };

// Classes
class Person {
  name: string;
  constructor(name: string) {
    this.name = name;
  }
}
let p = new Person("John");

// Type Aliases
type StringOrNumber = string | number;
let value: StringOrNumber = "Hello";

// Arrays
let numbers: number[] = [1, 2, 3];

// Tuples
let person: [string, number] = ["John", 30];

// Enums
enum Color {
  Red,
  Green,
  Blue
}
let color: Color = Color.Green;

// Type Assertions
let someValue: any = "hello";
let strLength: number = (<string>someValue).length;

// Any Type
let data: any = 42;
```