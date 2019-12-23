## My notes on node.js

## exporting modules
* we export modules in node js using `module.exports = variable` or `module.exports.export_name = variable` for multiple variables


## importing from files

```js
let app = require("./app.js");
```

## how to use events

```js
//call the events module
const events = require("events");
//create an event emitter object
let em = new events.EventEmitter();
//create a custom event
em.on('shout', (msg)=>{
 console.log(msg);
});
///emit the event
em.emit('shout', "hello world");
```

## create and start a server in node

```js
const http = require("http");
let port = 3000;
const server = http.createServer((req, res) => {
    res.writeHead(200,{
        "Content-Type":"text/plain"
    })
    res.end("hello world from tobecci");
});
server.listen(port);
console.log("server has started on " + port);
```

## reading a file in node js
```js
const fs = require("fs");
fs.readFileSync("filename.txt", "utf8");
//sync means its synchronous, its fully executed before any code below it runs
```

## some node modules

* path module
  * path.parser(__filename);


