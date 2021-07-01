# Basis

## What is NodeJs?

Node.js is an open-source and cross-platform JavaScript runtime environment, Node.js runs the V8 JavaScript engine, the core of Google Chrome, outside of the browser.

A simple Hello World in Node Js

```javascript
const http = require('http')

const hostname = '127.0.0.1'
const port = process.env.PORT

const server = http.createServer((req, res) => {
  res.statusCode = 200
  res.setHeader('Content-Type', 'text/plain')
  res.end('Hello World!\n')
})

server.listen(port, hostname, () => {
  console.log(`Server running at http://${hostname}:${port}/`)
})
```

This example is a simple HTTP server in NodeJs

* We create the server with the `http.createServer`
* We put the status code for the response
* The headers
* And when we have an incoming request, we send back the 'Hello World'
* Finally, we start the server with the `server.listen()`

This is how a simple HTTP server is created in NodeJs.

Basically NodeJs is a framework that allows us to execute JavaScript on the server side as we do on the client side.

## How NodeJs works

The syntax for NodeJs is the same as JavaScript as the framework is based on this language \(although it could also be used in Typescript\).

### Data types

It has the same data types as JS:

* String
* Number
* Boolean
* Null
* Undefined
* RegExp

And NodeJs adds another data type, the _Buffer_ this data type is mainly used to store binary data, while reading from a file or receiving packets via the network

### Process

As NodeJs runs on the server, we have access to the properties of the server, such as the process id, environment variables, path of files, etc.

```javascript
process.env.MY_ENV_VAR
// Name of env var

process.pid
// PID 45658
```

### Modules in NodeJs

One of the main differences of using NodeJs is the addition of modules, the modules are pieces of reusable code, that we can share between files.

{% tabs %}
{% tab title="Sum.js" %}
```javascript
// simple module to export a funcion

const sum = (a, b) => {
    return a + b
    }
    
exports.sum = sum
```
{% endtab %}

{% tab title="app.js" %}
```javascript
import {sum} from '/sum.js'

console.log(sum(4,5)

//9
```
{% endtab %}
{% endtabs %}

