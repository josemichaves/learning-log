# Axios

![](../../.gitbook/assets/image%20%2822%29.png)

Axios is a library that allows us to make requests to via http, it's a promise based which implies that always will return a promise.

## Syntax

The syntax for an axios request is quite easy and simple.

```typescript
axios.method('path').then((response) => {
    //code to execute
});
```

This is a simple request, and we'll display the result in the console.

```typescript
axios.get('https://random.api/user/?user=JohnSnow').then((user) => {
    console.log(user.data)
});

// {name: 'John', surname:'Snow'}
```

The response is an object with all the data that is sent to us from the API.

```typescript
{ // data is the response that was provided by the server data: {},
// status is the HTTP status code from the server response status: 200,
// statusText is the HTTP status message from the server response statusText: 'OK',
// headers the HTTP headers that the server responded with // All header names are lower cased and can be accessed using the bracket notation. // Example: response.headers['content-type'] headers: {},
// config is the config that was provided to axios for the request config: {},
// request is the request that generated this response // It is the last ClientRequest instance in node.js (in redirects) // and an XMLHttpRequest instance in the browser request: {} }

axios.get('https://random.api/user/?user=JohnSnow')
  .then(function (response) {
    console.log(response.data);
    console.log(response.status);
    console.log(response.statusText);
    console.log(response.headers);
    console.log(response.config);
  });
```

This is the structure of the object that sends back the API, inside we have all the information about this request, but as we only want to get the data of the user we access to the property `data` of the response object.

## Parameters in the request

In the path we need to specify the path where we'll make the request, we can specify strings or even parameters.

```typescript
axios.get('https://random.api/user/?user=JohnSnow').then((user) => {
    console.log(user.data)
});

// we can also pass the parameter apart.

axios
    .get("/user", {
        params: {
            user: "JohnSnow",
        },
    })
    .then((user) => {
        console.log(user.data);
    }));

// {name: 'John', surname:'Snow'}
```

## Instance

We also can create an instance for defining a default value such the path, a timeout, etc. And not passing it every time we make a request, we can define various parameters that will stay in all the requests

```typescript
const instance = axios.create({
    baseUrl: "https://randomuser.me",
    timeout: 1000
});
```

Now for making a request, we need to call to our `instance` instead to `axios`.

```typescript
instance.post('/api/newuser', {
    name: "Tyrion",
    surname: "Lannister"
}).then((res) => console.log(res.data))
```

## Interceptors

An interceptor allows us to deal with the requests before they arrive to the `.then()` or `catch`, for example, is useful when we need to attach a value to the headers, but the value itself can change over time, so every time we make a request we can handle it. We need to always return the request as thanks to this will follow the execution.

```typescript
instance.interceptors.request.use((req) => {
    req.headers.authorization = usertoken
    return req
})
```

## Error Handling

To deal with an error in Axios we can call a catch to the `axios`.

```typescript
instance.get('user/?user=AryaStark').catch((error) => {
    console.log(error.data.status, err: error.data.error)
})
/// 404, 'User AryaStark not found'
```

