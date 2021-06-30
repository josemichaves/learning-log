# Real Time Data

## What is real time data?

The real time data, is when a server is sending data at the moment to the client, normally with an HTTP request, the client sends a request and then the server send the response back, and also a client it's the only who can make requests, the server cannot send data back if the client doesn't make a request for it.

With real time data it's completely different, with the usage of the WebSocket protocol, a client and server can transmit data whenever they need to both parts. They open a connection with a handshake \(they accord to establish this connection and trusting each other\), and once the connection it's open they can start to share data.

![This is how WebSocket works](../../.gitbook/assets/image%20%2840%29.png)

## When we need to use real time data?

Think about a chat room, they need to send the data as soon as they have it, in this case, we'll establish a connection between the two parts and leaving this channel open to send data via this channel, and so the data will be in real time. If for example we have a cryptocurrency page, that shows a graph with the actual market share of specific coin, we would be tempted to use real time data to update this chart, but in this case it's not necessary because we don't need to know the data at every specific moment, we can make an HTTP request every 2 minutes to update this chart.

## How to use WebSocket

### Server side

On the server, we first need to crate the WebSocket server to transmit data, in this case we would use the library WebSocket Server.

```javascript
const wss = new WebSocket.Server({port: 80})
```

And that's it, we've already created our WebSocket server, now we need to define the method that we'll be executing in this WebSocket server.

The object wss have a lot of properties to deal with it, we're mainly focusing on sending data.

```javascript
wss.on('connection', (ws) => {
    ws.send('Hi client!')
}
```

That's a simple example of what happens with a client connects to the web socket server, the client connects and the websocket servers send the Hi client! As a response. The syntax is easy, first we call to the object was, then we declare the event, in this case with the on, and as a parameter we have various options, the first parameter it's the event when we want to trigger this method, and the second parameter it's a callback to happen when this method, it's called, inside the callback we also have another parameter called us, which is it the WebSocket it.

And that's it! Our server is sending a message when detects a connection from a client.

### Client side

In the client side, it's as easy as the backend, first we need to create the WebSocket, in this case we'll be using the API of the browser to deal with the WebSocket.

```javascript
const webSocket = new WebSocket('ws://webSocketAddress:80')
```

We've the webSocket created, now the WebSocket API of the browser, that's exponsing the `webSocket` object, have four properties

* onmessage
* onopen
* onclose
* onerror

This four properties allows us to deal with the different events that could be happening.

```javascript
webSocket.onMessage((event) => {
    const message = event.data
})
```

In this example we're saving the response in a variable

We first declare the object and the property we need to deal with, then inside we call the callback that has a parameter that's the event of the WebSocket, and then we execute the callback.

