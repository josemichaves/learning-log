# How to connect to an API Rest?

## Server Side

To connect to an API is quite easy and straightforward, there're a lot of ways, libraries to do it, but with NodeJs the most common and used library to acomplish that is ExpressJs.

```javascript
 app.listen(PORT, () =>
      console.log(`⚡️[server]: Server is running at http://localhost:${PORT}`)
    );
```

And that's it, we just need to connect our app to the port exposed by the API \(normally the 4000\) and listen in that port, so we can accept requests and send back the data.

## Client Side

In the client side we can use the built in method `fetch()` of JavaScript, a XMLHTTP request or libraries such Axios, Request, Superagent, etc.

### fetch\(\)

`fetch()` is a built in method in JavaScript to make requests to an URL, and dealing with the response.

```javascript
fetch("https://jsonplaceholder.typicode.com/posts/1")
  .then((response) => response.json())
  .then((json) => console.log(json));
```

We can also make async requests in fetch

```javascript
const getTest = async() => {
  const test = await fetch('https://localhost:4000/test')
  const data = await test.json()
  return data
};

getTest().then(data => console.log(data));
```

`fetch()` is a good option but lacks in error handling.

### axios

Axios is the best option to make a request to an API.

```javascript
axios.get("https://jsonplaceholder.typicode.com/posts/1").then(
  (response) => console.log(response.data),
  (err) => {
    console.error(err);
  }
);
```

As we can see in axios we can handle better the error in the request.

