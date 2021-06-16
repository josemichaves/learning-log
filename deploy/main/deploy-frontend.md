# Deploy frontend

When we want to serve a react project in to a server, the first thing we need to do is creating the static, because a server only can serve HTML and CSS not Javascript or scss.

## Build

To generate the static files of the React project, we can call the script that React provides us, which is it `build` we can call this script with `npm run build` and then React will generate our static files, is transpiling our tsx or jsx files into HTML. We also need to specify the environment variables at the moment of the build in order to maintain these in the static files.

## Upload to the server

Once we've generated the static files we need to upload to the server, we can do this with an FTP server like Filezilla.

## Serve the static

Once we have all the build files in the server, we need to put these static in the default location of the web server that we've decided to use \(the two most famou and uses are Ngnix and Apache\)

In nginx the default path is `usr/share/nginx/html`



And that's it, our react project is served to the web and, then we can connect our web project to a server and database and have the same functionalities that we had in the development environment.

