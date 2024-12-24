# NPM
**npm** is the standard package manager for Node.js

**local packages** are installed in the directory where you run npm install <package-name>, and they are put in the node_modules folder

**global packages** are all put in a single place in your system, regardless of where you run npm install -g <package-name>

The **@** symbol is used to denote a scoped package, which is a way to group related npm packages under a namespace
npm install @nestjs/core

**package.json**
file holds various metadata relevant to the project,This file is used to give information to npm that allows it to identify the project as well as handle the project's dependencies

Node.js always runs require synchronously. If you require an external module from within functions your module will be synchronously loaded when those functions run

# require vs ES6 import

**require**:
Type: CommonJS module system

Usage: Used in Node.js environments

Behavior: Loads modules synchronously at runtime

Flexibility: Can be called conditionally or dynamically (inside if)

**import**:
Type: ES6 module system.

Usage: Works in modern JavaScript

Behavior: Statically analyzed; must be at the top level
```javascript
if (condition) {
  import('./module').then(module => {
    module.doSomething();
  });
}
```