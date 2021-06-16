# Deploy backend

In order to deploy a backend service in a server we need to follow various steps.

## Compile Typescript

If we're building our project with Typescript the first thing we need to do is to generate the JS files to our server, in order to transform all the types and TS code in JavaScript.

We can do this with the script `tsc` which will build our file in JavaScript, it will compile all our TS in JS.

Then we need to serve our files into the server.

## Upload to the server

Normally we'll connect to our server via SSH, SSH is a form of connecting remotely to another machine in the terminal. Once we're connected we can upload our code into the server, we can do it in two ways.

* Compile in the server: We can compile our TS in the server \(first we'll need to upload our code to the server, we can do it via the GitHub clone\).
* Upload the compiled files: We can upload the files to our server via an FTP server, we can upload the files that we have in local to the remote server.

Once we have the build files in the server, we can start our server.

## Starting the server

In order to start the server we just need to call the start of the main file of the project. We can do it with the method of the framework, in this case we would use NodeJs.

We can use the method of the NodeJs which is `node index.js` and we can use also other libraries such as PM2 or Forever.

The syntax is similar we just need to call to the main files.

## Opening ports

Before deploying anything we need to make sure that the port that we'll be using are open and accessible.

### Environment variables

At the time to start our server, we need to specify our environment variables, in order to make it all work. 

The environment variables are variables, that we've defined before, but they're not accessible in the code, so we need to specify them as inline parameter.

One common use of the environment variables is to assign ports and address, imagine we have an env var called PORT and we want this app to be up in the port 5500, all we need to do is something like that `PORT=5500 pm2 index.js`.



And that's it, we'll have our server deployed and ready to accept connections.

