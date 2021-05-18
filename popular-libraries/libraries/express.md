# Express

![](../../.gitbook/assets/image%20%2815%29.png)

## Initalization

ExpressJs is a back-end framework for NodeJs, this framework, it's fast, flexible and minimalist. It lets us create API's easy and manage routes, static files, templates, integration with databases \(such as MongoDB or Postgres\), error handling and middlewares among many other.

To start using we need to create an Express server, doing this is quite easy.

First of all we need to create our express app, which we'll use to manage all the traffic, then we need to declare a port where we'll be receiving the requests, and finally we'll start the server.

```javascript
const app = express();

const port = 3000;

app.listen(port, () => {
    console.log(`server started in port ${port}`)
});
```

Right now we have our server started and therefore we're listening in the port 3000, so every request that we make forthis port we can handle it via express.

## Methods to request

We have four methods to make a request to a server

1. **GET**: Get is for when we want to obtain data from the server or API. \(I.e. A list of places available\).
2. **POST**: Post is for when we want to insert data in the server, API, DB, etc. \(I.e. A new place in the list\).
3. **PUT**: Put is for when we want to update data in the server, API or DB\(I.e. A place now it's visited\).
4. **DELETE**: Delete is for when we want to remove data from the API \(I.e. Remove item in the list\).

Depending on this we'll have different properties in our express app.

If we want to get the places available, we'll use Get. We'll call the get method, and we need to pass a parameter which is what path will be executing this code, then the second parameter is to deal with the request itself, req stands for request and res for response, we have various methods in req and res, in this case we're using `res.send()` which returns the data we specify.

```javascript
app.get('/places', (req, res) => {
    res.send(['place1', 'place2', 'place3'])
})
```

Same in Post, but in the Post normally we need to deal with the req parameter. In the req we can have various ways to data to come, body, params, query, headers, etc... Every has its own call. Here we're creating a new place and we're getting the data from the body, assigning it to a new variable, and then send it to the DB, finally we return an ok to notice the creation was correct.

```javascript
app.post('/newPlace', (req, res) => {
    const place = {
        name: req.body.name,
        city: req.body.city
    }); introduceNewEntryInDB(place); res.send({
    ok: true,
    err: ''
});
});
```

The Put method allows us to update an entry. In this one we'll specify the place we want to update via the path we send the request, to declare a variable inside express we can do it like this `:variable`, with this we can deal with this variable even if we don't know the exact value of it.

```javascript
app.put('place/:placeName', (req, res) => {
    modifyPlaceInDB(req.params.placeName);
    res.send({
        ok: true,
        err: ''
    });
});
```

And finally the Delete, we we'll delete an entry in the DB, but using the same path we use to modify an  existing place, Express allows us to use the same path to different purposes if the method changes.

```javascript
app.put('place/:placeName', (req, res) => {
    modifyPlaceInDB(req.params.placeName);
    res.send({
        ok: true,
        err: ''
    });
});
```

## Syntax

So the syntax for Express is the following

```javascript
app.METHOD(PATH, HANDLER)
```

## Middleware

Also one of the superpowers of Express it's the ability to write middleware, a middleware, it's a function that will execute every time a request is done, so we can filter the request with only one function and not calling it all the time.

The main difference of writing a middleware is the adding of a third parameter in the handler the `next()` parameter, what this parameter does it's to follow the execution of the request once we want, in this case we will verify if the user has a token in the headers of the request. If it's user we'll follow the execution, if not we'll throw a status code of 401 \(Unauthorized\) and an error.

```javascript
app.use((req, res, next) => {
    if (req.headers.token) {
        next()
    } else {
        res.send({
            ok: false,
            err: 'No token in headers'
        }).status(401)
    }
})
```

We can also use this function only when we need, as the middleware above will execute for every request we make no matter what method or path uses.

```javascript
const hasToken = (req, res, next) => {
    if (req.headers.token) {
        next()
    } else {
        res.send({
            ok: false,
            err: 'No token in headers'
        })
    }
}

app.post('/newPlace', hasToken, (req, res) => {
    const place = {
        name: req.body.name,
        city: req.body.city
    }); introduceNewEntryInDB(place); res.send({
    ok: true,
    err: ''
});
});
```

