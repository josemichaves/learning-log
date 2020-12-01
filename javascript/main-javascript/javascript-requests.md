# JavaScript Requests



1. JavaScript is the language of the web because of its asynchronous capabilities. AJAX, which stands for Asynchronous JavaScript and XML, is a set of tools that are used together to take advantage of JavaScript’s asynchronous capabilities.
2. There are many HTTP request methods, two of which are GET and POST.
3. GET requests only request information from other sources.
4. POST methods can introduce new information to other sources in addition to requesting it.
5. GET requests can be written using an XMLHttpRequest object and vanilla JavaScript.
6. POST requests can also be written using an XMLHttpRequest object and vanilla JavaScript.
7. Writing GET and POST requests with XHR objects and vanilla JavaScript requires constructing the XHR object using `new`, setting the `responseType`, creating a function that will handle the response object, and opening and sending the request.
8. To add a query string to a URL endpoint you can use `?` and include a parameter.
9. To provide additional parameters, use `&` and then include a key-value pair, joined by `=`.
10. Determining how to correctly write the requests and how to properly implement them requires carefully reading the documentation of the API with which you’re working.
    1. GET and POST requests can be created a variety of ways.
    2. Use AJAX to asynchronously request data from APIs. `fetch()` and `async`/`await` are new functionalities developed in ES6 \(promises\) and ES8 respectively.
    3. Promises are a new type of JavaScript object that represent data that will eventually be returned from a request.
    4. `fetch()` is a web API that can be used to create requests. `fetch()` will return promises.
    5. We can chain `.then()` methods to handle promises returned by `fetch()`.
    6. The `.json()` method converts a returned promise to a JSON object.
    7. `async` is a keyword that is used to create functions that will return promises.
    8. `await` is a keyword that is used to tell a program to continue moving through the message queue while a promise resolves.
    9. `await` can only be used within functions declared with `async`.

