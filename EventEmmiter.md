# EventEmitter

An EventEmitter in Node.js is asynchronous by default.

EventEmitter emits events and executes the event listeners asynchronously. When an event is triggered, the listeners are invoked in the next iteration of the event loop, meaning they are queued up and executed after the current execution context finishes.


```javascript
const EventEmitter = require('events');

// Create an instance of EventEmitter
const emitter = new EventEmitter();

// Event listener
emitter.on('event', () => {
  console.log('Event listener 1');
});

emitter.on('event', () => {
  console.log('Event listener 2');
});

console.log('Before emitting event');
emitter.emit('event');
console.log('After emitting event');
```

Output

Before emitting event
After emitting event
Event listener 1
Event listener 2