# JavaScript Asynchronous



Promises are JavaScript objects that represent the eventual result of an asynchronous operation.

Promises can be in one of three states: pending, resolved, or rejected.

A promise is settled if it is either resolved or rejected.



```javascript
const promise1 = new Promise((resolve, reject) => {
    resolve('foo');
    reject('Fail');
});
```

We construct a promise by using the `new` keyword and passing an executor function to the `Promise` constructor method.



```javascript
const promise1 = new Promise((resolve, reject) => {
  setTimeout(() => {
    resolve('foo');
  }, 300);
});
```

`setTimeout()` is a Node function which delays the execution of a callback function using the event-loop.



```javascript
const promise1 = new Promise((resolve, reject) => {
  setTimeout(() => {
    resolve('foo');
  }, 300);
});

promise1.then((value) => {
  console.log(value);
});

>>>foo
```

We use `.then()` with a success handler callback containing the logic for what should happen if a promise resolves.





```javascript
const promise1 = new Promise((resolve, reject) => {
    setTimeout(() => {
        resolve('foo');
    }, 300);
});

promise1.then((value) => {
    console.log(value);
});

promise1.catch((value) => {
    console.log(fail)

>>> foo
```

We use `.catch()` with a failure handler callback containing the logic for what should happen if a promise rejects.

Promise composition enables us to write complex, asynchronous code that’s still readable. We do this by chaining multiple `.then()`‘s and `.catch()`‘s.

To use promise composition correctly, we have to remember to `return` promises constructed within a `.then()`.

We should chain multiple promises rather than nesting them.

```javascript
const promise1 = Promise.resolve(3);
const promise2 = 42;
const promise3 = new Promise((resolve, reject) => {
  setTimeout(resolve, 100, 'foo');
});

Promise.all([promise1, promise2, promise3]).then((values) => {
  console.log(values);
});
// expected output: Array [3, 42, "foo"]
```

To take advantage of concurrency, we can use `Promise.all()`. The **`Promise.all()`** method takes an iterable of promises as an input, and returns a single promise that resolves to an array of the results of the input promises. This returned promise will resolve when all of the input's promises have resolved, or if the input iterable contains no promises. It rejects immediately upon any of the input promises rejecting or non-promises throwing an error, and will reject with this first rejection message / error.

