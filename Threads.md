# Threads
Node.js is designed to be single-threaded, operating primarily on an event-driven architecture using the event loop. However, it provides mechanisms to leverage additional threads when needed

**Worker Threads**

Workers communicate with the main thread using message passing (via postMessage and onmessage).

```javascript
const { Worker } = require('worker_threads');

if (isMainThread) {
  const worker = new Worker('./worker.js'); // Worker script
  worker.postMessage('Hello, Worker!');
  worker.on('message', (message) => {
    console.log('Message from worker:', message);
  });
} else {
  parentPort.on('message', (message) => {
    console.log('Message from main thread:', message);
    parentPort.postMessage('Hello, Main Thread!');
  });
}

```

**Child Processes**

The child_process module enables spawning child processes to execute external programs or scripts

**spawn()**: Executes a command.

**exec()**: Executes a command with a buffer for the output.

**fork()**: Spawns a new Node.js process with IPC enabled for communication.

```javascript
const { fork } = require('child_process');

const child = fork('./child.js'); // Fork a new process
child.send('Hello, Child Process!');
child.on('message', (message) => {
  console.log('Message from child:', message);
});

```