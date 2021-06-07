# REST API

![](../../.gitbook/assets/image%20%2827%29.png)

## What is REST?

REST is a set of architectural constraints, not a protocol or a standard. API developers can implement REST in a variety of ways.

When a client request is made via a RESTful API, it transfers a representation of the state of the resource to the requester or endpoint. This information, or representation, is delivered in one of several formats via HTTP: JSON \(Javascript Object Notation\), HTML, XLT, Python, PHP, or plain text. JSON is the most generally popular programming language to use because, despite its name, it’s language-agnostic, as well as readable by both humans and machines. 

Something else to keep in mind: Headers and parameters are also important in the HTTP methods of a RESTful API HTTP request, as they contain important identifier information as to the request's metadata, authorization, uniform resource identifier \(URI\), caching, cookies, and more. There are request headers and response headers, each with their own HTTP connection information and status codes.

In order for an API to be considered RESTful, it has to conform to these criteria:

* A client-server architecture made up of clients, servers, and resources, with requests managed through HTTP.
* [Stateless](https://www.redhat.com/en/topics/cloud-native-apps/stateful-vs-stateless) client-server communication, meaning no client information is stored between get requests and each request is separate and unconnected.
* Cacheable data that streamlines client-server interactions.
* A uniform interface between components so that information is transferred in a standard form. This requires that:
  * resources requested are identifiable and separate from the representations sent to the client.
  * resources can be manipulated by the client via the representation they receive because the representation contains enough information to do so.
  * self-descriptive messages returned to the client have enough information to describe how the client should process it.
  * hypertext/hypermedia is available, meaning that after accessing a resource the client should be able to use hyperlinks to find all other currently available actions they can take.
* A layered system that organizes each type of server \(those responsible for security, load-balancing, etc.\) involved the retrieval of requested information into hierarchies, invisible to the client.
* Code-on-demand \(optional\): the ability to send executable code from the server to the client when requested, extending client functionality. 

## How to interact with a REST API?

A REST API is based on the CRUD operators. 

* GET: To retrieve data from the API. 
* PUT: To update data from the API. 
* DELETE: To remove data from the API. 
* POST: To insert data in the API. 

When we create a REST API we also create the endpoints for this API, this is the path where the services will make his request and then do what they need with the response.

## Endpoints in a REST API

One important thing is how we declare our endpoints, we need to nest this path to acquire what we want for example, if we have an endpoint to get the tickets from a cinema, we can filter them and so on, for example this way:

* GET /tickets - Return all the tickets.
* GET /tickets/12 - Return only the ticket 12.
* POST /tickets - Create a new ticket.
* PUT /tickets/12 - Update the ticket 12.
* DELETE /tickets/12 - Deletes the ticket 12.

What we accomplish doing this is to have our endpoints reusable and standardized.

## HTTP Status codes

We always need to send a response code accordingly to what we've done in the API, if there's a failure on the server side, we'll throw a status code 500, if the request doesn't find a 404, if we created a user a 201 or if just an OK that the operations successfully completed a 200. Doing this we always get a receipt in the client of what is happening on the server.



