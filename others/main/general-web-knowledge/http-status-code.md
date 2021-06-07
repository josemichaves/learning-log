# HTTP Status code

The HTTP status code allows us to send a code saying what just happened, if there's an error, if the operation was successful or if we're redirecting to another path.

## Informational responses \(100 - 199\)

* 100 \(Continue\) - It means that everything is OK and the client can continue.
* 101 \(Switching protocol\) - In indicates the servers is changing the protocol \(i.e. from HTTP to Web Socket\)

## Successful responses \(200-299\)

* 200 \(OK\)  - Te request has succeed, the meaning depends on the HTTP method:
  * `GET`: The resource has been fetched and is transmitted in the message body.
  * `HEAD`: The representation headers are included in the response without any message body.
  * `PUT` or `POST`: The resource describing the result of the action is transmitted in the message body.
* 201 \(Created\) - Is the usual response for a `POST` method, the request has succeed and a new resource is created.
* 204 \(No content\) - The request was successful but no response is returned, it's useful when you've only updated the headers.

## Redirects \(300-399\)

* 301 \(Moved permanently\) - This URL of the requested method has changed, the new URL is in the body of the response.

## Client error responses \(400-499\)

* 400 \(Bad request\) - The server could not understand the request, due to invalid syntax.
* 401 \(Unauthorized\) - You need to be authorized \(logged, given permission of the administrator, etc\) in order to use this endpoint.
* 403 \(Forbidden\) - The same as 401, but in this case the server knows your identity, but this content is restricted to you.
* 404 \(Not found\) - This means that the request was not found, if in the client side it's the URL doesn't exits, if in the server side, the endpoint is valid, but nothing was found to return. This code is one of the most used.
* 405 \(Not allowed\) -  The request method exists, but it's not allowed to use \(i.e. some DELETES in a public API\)
* 408 \(Request timeout\) - The request take to long to respond and therefore was cancelled.
* 418 \(I'm a teapot\) - It's a error response for April Fool's but some websites respond when this code when they don't want to return a status code.
* 429 \(Too many requests\) - The user has sent too many requests \("rate limiting"\).

## Server error responses \(500-599\)

* 500 \(Internal server error\) - The server has encountered a situation it doesn't know to handle.
* 502 \(Bad gateway\) - This error response means that the server, while working as a gateway to get a response needed to handle the request, got an invalid response.
* 503 \(Service unavailable\) - The server is not ready to handle the request, common causes is the server is down or had an overload.
* 504 \(Gateway timeout\) - This error response is given when the server is acting as a gateway and cannot get a response in time.
* 508 \(Loop detected\) - An infinite loop while proceeding the request.
* 511 \(Network authentication required\) - You must be authorized in order to make requests.

