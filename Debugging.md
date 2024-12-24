How do you debug Node.js applications?

# Using console.log()
```javascript
const add = (a, b) => {
  console.log('a:', a, 'b:', b);  // Debugging log
  return a + b;
};

console.log(add(2, 3));  // Output: 5
```

# using Node.js Built-in Debugger

Start the app with the inspect flag: **node inspect app.js**

and you can interact with it using commands like cont (continue), next, step, and repl
```javascript
const add = (a, b) => {
  debugger;  // This will pause execution here
  return a + b;
};

add(2, 3);
```

# Using Chrome DevTools

node --inspect-brk app.js

Open Chrome and go to chrome://inspect

Click on Inspect next to your Node.js app to open the DevTools interface




