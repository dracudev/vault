| Concept         | Description                                                              | Syntax Example                                                                                         |
| --------------- | ------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------ |
| Installing Jest | Installing Jest testing framework via npm.                               | `npm install --save-dev jest`                                                                          |
| Basic Test      | A basic test function to check if a condition is true.                   | `test('adds 1 + 2 to equal 3', () => { expect(1 + 2).toBe(3); });`                                     |
| `expect()`      | Jest's assertion function used to test values.                           | `expect(value).toBe(expected);`                                                                        |
| `toBe()`        | A matcher to check if a value is equal to the expected value.            | `expect(2 + 2).toBe(4);`                                                                               |
| `beforeEach()`  | Runs a function before each test case to set up the testing environment. | `beforeEach(() => { /* Setup code here */ });`                                                         |
| `afterEach()`   | Runs a function after each test case to clean up.                        | `afterEach(() => { /* Cleanup code here */ });`                                                        |
| Mock Functions  | Used to create mock implementations of functions to test function calls. | `const mockFn = jest.fn();`                                                                            |
| `describe()`    | Grouping related tests together for better organization.                 | `describe('Addition tests', () => { test('adds 1 + 1 to be 2', () => { expect(1 + 1).toBe(2); }); });` |
| `it()`          | Similar to `test()`, used to define individual test cases.               | `it('should add 1 and 2 to be 3', () => { expect(1 + 2).toBe(3); });`                                  |
| `toEqual()`     | Matcher to compare objects or arrays to check if they are deeply equal.  | `expect({a: 1}).toEqual({a: 1});`                                                                      |
```js
// Basic Test
test('adds 1 + 2 to equal 3', () => {
  expect(1 + 2).toBe(3);
});

// expect() and toBe()
test('adds 1 + 1 to be 2', () => {
  expect(1 + 1).toBe(2);
});

// beforeEach() and afterEach()
let counter = 0;
beforeEach(() => {
  counter = 0;  // Reset counter before each test
});
afterEach(() => {
  // Cleanup if needed after each test
});

test('increments counter', () => {
  counter++;
  expect(counter).toBe(1);
});

// Mock Functions
const mockFn = jest.fn();
mockFn('hello');
expect(mockFn).toHaveBeenCalledWith('hello');

// describe() for grouping tests
describe('Addition tests', () => {
  test('adds 1 + 1 to be 2', () => {
    expect(1 + 1).toBe(2);
  });
  
  test('adds 2 + 2 to be 4', () => {
    expect(2 + 2).toBe(4);
  });
});

// it() for individual tests
it('should add 1 and 2 to be 3', () => {
  expect(1 + 2).toBe(3);
});

// toEqual() for comparing objects or arrays
test('object equality', () => {
  expect({ a: 1 }).toEqual({ a: 1 });
});
```