| Method           | Description                                                                                                         | Syntax Example                                      |
| ---------------- | ------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------- |
| `resolve()`      | Returns a promise that is resolved with a given value.                                                              | `let promise = Promise.resolve("Success!");`        |
| `reject()`       | Returns a promise that is rejected with a given reason.                                                             | `let promise = Promise.reject("Error!");`           |
| `then()`         | Adds a callback to be executed when the promise is resolved.                                                        | `promise.then(result => { console.log(result); });` |
| `async function` | Defines a function that returns a promise and can be used with `await` inside to handle asynchronous operations.    | `async function example() { return "Hello"; }`      |
| `await`          | Pauses the execution of an async function until a promise is resolved. Can only be used inside an `async` function. | `let result = await promise;`                       |
```js
// resolve()
let promise = Promise.resolve("Success!");
promise.then(result => {
  console.log(result);  // "Success!"
});

// reject()
let promise = Promise.reject("Error!");
promise.catch(error => {
  console.log(error);  // "Error!"
});

// then()
let promise = Promise.resolve("Resolved!");
promise.then(result => {
  console.log(result);  // "Resolved!"
});

// async function
async function example() {
  return "Hello";
}
example().then(result => {
  console.log(result);  // "Hello"
});

// await
async function getData() {
  let promise = new Promise((resolve, reject) => {
    setTimeout(() => resolve("Data fetched!"), 2000);
  });
  
  let result = await promise;
  console.log(result);  // "Data fetched!"
}

getData();
```