# Node.JS
## What Is Node.js ?

*Node.js is an event-based, non-blocking, asynchronous I/O runtime that uses Google’s V8 JavaScript engine and libuv library.*

## Node Binaries vs Version Manager

*Many websites will recommend that you head to the official Node download page and grab the Node binaries for your system. While that works, I would suggest that you use a version manager instead. This is a program that allows you to install multiple versions of Node and switch between them at will. There are various advantages to using a version manager. For example, it negates potential permission issues when using Node with npm and lets you set a Node version on a per-project basis.*

### how to log “Hello, World!” by the Node.js Way ?

You can check that Node is installed on your system by opening a terminal and typing `node -v`. If all has gone well, you should see something like `v12.14.1` displayed. This is the current LTS version at the time of writing.

Next, create a new file `hello.js` and copy in the following code:

`console.log("Hello, World!");`

This uses Node’s built-in console module to display a message in a terminal window. To run the example, enter the following command:

`node hello.js`

If Node.js is configured properly, “Hello, World!” will be displayed.

 *here’s a second program that makes use of several modern JavaScript features, such as tagged template literals, object destructuring and `Array.prototype.flatMap()`:*

 `function upcase(strings, ...values) {`

  `return values.map(name => name[0].toUpperCase() + name.slice(1)).join(' ') + strings[2];`

`}`

`const person = {`

  `first: 'brendan',`

  `last: 'eich',`

  `age: 56,`

  `position: 'CEO of Brave Software',`

`};`

`const { first, last } = person;`

`const emoticon = [ ['┌', '('], ['˘', '⌣'], ['˘', ')', 'ʃ'] ];`


`console.log(upcase`${first} ${last} is the creator of JavaScript! ` + emoticon.flat().join('')`

`);`

## Introducing npm, the JavaScript Package Manager

*In addition to being the package manager for JavaScript, npm is also the world’s largest software registry. There are over 1,000,000 packages of JavaScript code available to download, with billions of downloads per week. Let’s take a quick look at how we would use npm to install a package.*

### What Is Node.js Used For ?

*it's used for  installing (via npm) and running (via Node) various build tools — designed to automate the process of developing a modern JavaScript application.*

## The Node.js Execution Model

*Node.js, however, is single-threaded. It’s also event-driven, which means that everything that happens in Node is in reaction to an event. For example, when a new request comes in (one kind of event) the server will start processing it. If it then encounters a blocking I/O operation, instead of waiting for this to complete, it will register a callback before continuing to process the next event.*

**The following image depicts Node’s execution model:**

![nodejs](https://uploads.sitepoint.com/wp-content/uploads/2012/10/1516152673node_event_loop.png)

## “Hello, World!” — Server Version

**Let’s have a quick look at a “Hello, World!” example HTTP server:**

`const http = require('http');`

`http.createServer((request, response) => {`
  
  `response.writeHead(200);`

  `response.end('Hello, World!');`
  
  `}).listen(3000);`

`console.log('Server running on http://localhost:3000');`

*To run this, copy the code into a file named hello-world-server.js and run it using node hello-world-server.js. Open up a browser and navigate to http://localhost:3000 to see “Hello, World!” displayed in the browser.*

## What Are the Advantages of Node.js ?

- You can do everything in the same language, which, as a developer, makes you more productive (and hopefully, happier). For example, you can easily share code between the server and the client.

- Another of Node’s big pluses is that it speaks JSON. JSON is probably the most important data exchange format on the Web, and the lingua franca for interacting with object databases (such as MongoDB). 

- Finally, JavaScript is ubiquitous: most of us are familiar with JavaScript, or have used it at some point. This means that transitioning to Node development is potentially easier than to other server-side languages.


