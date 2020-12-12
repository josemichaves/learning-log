# JavaScript Async Await

An async function is a function declared with the `async`keyword, an async function awaits until the waiting condition is true to execute the code.`async...await` is syntactic sugar built on native JavaScript promises and generators.



We declare an async function with the keyword `async`.

Inside an `async` function we use the `await` operator to pause execution of our function until an asynchronous action completes and the awaited promise is no longer pending .

`await` returns the resolved value of the awaited promise.

We can write multiple `await` statements to produce code that reads like synchronous code.

```javascript
function resolveAfter2Seconds() {
    return new Promise(resolve => {
        setTimeout(() => {
            resolve('resolved')
        }, 2000);
    })
}

async function asyncCall() {
    console.log('calling...');
    const result = await resolveAfter2Seconds();
    console.log(result);
}

asyncCall();

>>>calling...
//2 seconds later
>>>resolved
```



We use `try...catch` statements within our `async` functions for error handling.

```javascript
try {
    testFunction('hello')
} catch (err) {
    console.log('There\'s an error')
}

>>>There's an error
```



We should still take advantage of concurrency by writing `async` functions that allow asynchronous actions to happen in concurrently whenever possible.

