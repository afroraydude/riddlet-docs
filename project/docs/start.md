# Your first Riddlet Server

Starting up your first Riddlet Server is simple. You actually only need to place one line inside of your server.js file.

```js
var riddlet = require("riddlet-server").Riddlet()
```

Then in your terminal, run `node server.js` and Riddlet will run on either your `port` environment variable or port 8000.

If you want to attach it to an already existing HTTP server, just attach it.

```js
var http = require('http');
 
app = http.createServer();
 
var riddlet = require("riddlet-server").Riddlet(app)
 
const port = process.env.port || 8080;
app.listen(port);
console.log("http listening on port ", port);
```

Make sure that the current directory of your `js` file can be written to and read from. This is necessary for any version above `v0.10.6`