# 🚀 Nodejs Roadmap

Node.js® is a JavaScript runtime built on Chrome's V8 JavaScript engine.
![Local Image](Nodejsworker.jpeg)

Node.js is a runtime environment for executing JavaScript code server-side.

In short, Node.js uses a single thread to handle multiple requests asynchronously, making it scalable and efficient for handling I/O-heavy applications.

# V8 JavaScript engine
The V8 library provides Node.js with a JavaScript engine :

a program that converts Javascript code into lower level or machine code that microprocessors can understand, which Node.js controls via the V8 C++ API. V8 is maintained by Google, for use in Chrome.

# Libuv
libuv is a C library that is used to abstract non-blocking I/O operations to a consistent interface across all supported platforms. It provides mechanisms to handle file system, DNS, network, child processes, pipes, signal handling, polling and streamin



# Error prefer Error-First Callback
```javascript
fs.readFile(filePath, function(err, data) {
  if (err) {
    //handle the error
  }
  // use the data object
});
```

**process.cwd()** is a method of global object process, returns a string value which is the current working directory of the Node.js process

**__dirname** is the directory name of the current script as a string value

# Some built-in Globals in Nodejs

**true globals**

**global** Setting a property to this namespace makes it globally visible within the running process

**process** which provides interaction with the current Node.js process

**console** which wraps various STDIO functionality in a browser-like way

**setTimeout()**, **clearTimeout()**, **setInterval()**, **clearInterval()** The built-in timer functions are globals

**pseudo-globals**

**module** ,**module.exports**, **exports**,**__filename**, **__dirname**, **require**






