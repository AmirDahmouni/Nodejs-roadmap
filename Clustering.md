# Node.js Built-in Cluster VS PM2 clustering

The choice between Node.js built-in cluster and PM2 clustering depends on your project's requirements, deployment environment

**Node.js Built-in Cluster**: A native module to enable clustering by forking multiple worker processes.

Use Case (Small/Custom Projects): When you need custom clustering logic and are comfortable managing processes manually.


# When would you use cluster module in Node.js ?

**Improve Scalability for I/O-Intensive Applications**

**Utilize Multi-Core CPUs**

**Isolate Crashing Workers**

**Balance Load Across Processes**

**Development and Testing for Production Environments**

Example

```javascript
const cluster = require('cluster');
const http = require('http');
const numCPUs = require('os').cpus().length;

if (cluster.isMaster) {
  console.log(`Master ${process.pid} is running`);

  // Fork workers for each CPU core
  for (let i = 0; i < numCPUs; i++) {
    cluster.fork();
  }

  cluster.on('exit', (worker, code, signal) => {
    console.log(`Worker ${worker.process.pid} died. Restarting...`);
    cluster.fork(); // Restart worker on crash
  });
} else {
  // Workers share the same port
  http.createServer((req, res) => {
    res.writeHead(200);
    res.end('Hello, World!');
  }).listen(8000);

  console.log(`Worker ${process.pid} started`);
}
```

# When Not to Use the Cluster Module ?

**CPU-Intensive Workloads**

**Small Applications**


