# 🚀 Nodejs Roadmap

Node.js® is a JavaScript runtime built on Chrome's V8 JavaScript engine.
![Local Image](Nodejsworker.jpeg)

# V8 JavaScript engine
The V8 library provides Node.js with a JavaScript engine :

a program that converts Javascript code into lower level or machine code that microprocessors can understand, which Node.js controls via the V8 C++ API. V8 is maintained by Google, for use in Chrome.

# Libuv
libuv is a C library that is used to abstract non-blocking I/O operations to a consistent interface across all supported platforms. It provides mechanisms to handle file system, DNS, network, child processes, pipes, signal handling, polling and streamin

# NPM
npm is the standard package manager for Node.js

# Beneficts of using Node.js
**Aynchronous and Event Driven** All APIs of Node.js library are aynchronous that is non-blocking
**Single Threaded but highly Scalable**: Node.js uses a single threaded model with event looping
**Very Fast**  Being built on Google Chrome's V8 JavaScript Engine, Node.js library is very fast in code execution
**No Buffering** Node.js applications never buffer any data. These applications simply output the data in chunks

# Aynchronous API
All APIs of Node.js library are aynchronous that is non-blocking

# Error prefer Error-First Callback
```javascript
fs.readFile(filePath, function(err, data) {
  if (err) {
    //handle the error
  }
  // use the data object
});
```


