### Conditional Statements

- **`if`** statement: allow you to control the flow of execution based on specific conditions. They help in making decisions and executing different blocks of code based on whether certain conditions are true or false.
```c
if (condition) {
    // Code to execute if condition is true
}
```
- **`if-else`** statement: allows you to execute one block of code if the condition is true and another block of code if the condition is false.
```c
if (condition) {
    // Code to execute if condition is true
} else {
    // Code to execute if condition is false
}
```
- **`switch`** statement: used to execute one statement from multiple possible choices based on the value of an expression.
```c
switch (expression) {
    case value1:
        // Code to execute if expression is equal to value1
        break;
    case value2:
        // Code to execute if expression is equal to value2
        break;
    default:
        // Code to execute if expression does not match any case
}
```
### Loops

- **`for`** loop: used when the number of iterations is known beforehand.
```c
for (initialization; condition; increment) {
    // Code to be executed repeatedly
}
```
- **`while`** loop: used when the number of iterations is not known beforehand and depends on a condition.
```c
while (condition) {
    // Code to be executed repeatedly
}
```
- **`do-while`** loop: similar to the `while` loop but guarantees that the loop body executes at least once before checking the loop condition.
```c
do {
    // Code to be executed repeatedly
} while (condition);
```