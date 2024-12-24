# Types of Streams in Node.js

**Readable Streams**
File streams, HTTP requests
```javascript
const fs = require('fs');
const readable = fs.createReadStream('file.txt', { encoding: 'utf8' });
readable.on('data', (chunk) => {
  console.log(chunk);
});
readable.on('end', () => {
  console.log('Finished reading.');
});
```


**Writable Streams**
File streams, HTTP responses
```javascript
const fs = require('fs');
const writable = fs.createWriteStream('output.txt');
writable.write('Hello, World!\n');
writable.end();
writable.on('finish', () => {
  console.log('Finished writing.');
});

```

**Duplex Streams**
Network sockets, custom streams
```javascript
const { Duplex } = require('stream');
const duplex = new Duplex({
  read(size) {
    this.push('Hello, Duplex!');
    this.push(null);
  },
  write(chunk, encoding, callback) {
    console.log(`Writing: ${chunk.toString()}`);
    callback();
  },
});
duplex.on('data', (chunk) => console.log(`Reading: ${chunk}`));
duplex.write('Duplex Stream Example');
duplex.end();
```

**Transform Streams**
Compression, encryption
```javascript
const { Transform } = require('stream');
const transform = new Transform({
  transform(chunk, encoding, callback) {
    this.push(chunk.toString().toUpperCase());
    callback();
  },
});
transform.on('data', (chunk) => console.log(`Transformed: ${chunk}`));
transform.write('hello');
transform.write('world');
transform.end();
```

