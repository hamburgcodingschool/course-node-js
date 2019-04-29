# Session 1

## Introduction

What is Node.js?
- Engine / Runtime
- server-side
- in a single thread
- explain: what is a Thread
- implemented asynchronically
- runtime / framework
- based on V8 engine

## Event loop

How does it work?
- there is an infinite loop running: the event loop
- is running on that single thread and processes everything that is happening in there
- you remember setTimeout()?
- the whole phases (timers, callbacks, idle/prepare, poll, check, close) are repeated over and over

## Node Project Setup

Task for today
- today we will take our project and let node.js deliver our html

Project setup
- in general, we have folders for different parts of the application, e.g. database, ...

Task:
- create a folder for your project
- open console
- run `npm init` 
- description: put something that helps you remember what you did here
- entry point: index.js
- test: skip
- git repository: https://github.com/hamburgcodingschool/April_2019
- enter your name
- skip the rest (always enter)
- Is this ok? yes

NPM
- is a package manager
- you can install packages with it
- either globally, that you can use them on the computer
- or locally, that you can use them on your project
- creates a folder `node_modules`
- `package.json` is the file where we write all our packages that we want to have installed for our project

`index.js`
- this is our entry point
- the file that we mention in our `package.json`

Task:
- in your `index.js` file, make some output with `console.log()`
- so that you see that it's working
- to run it, run `node index.js`

HTTP
- node.js works with HTTP
- it delivers our HTML, CSS, JS
- certain libraries (packages) help with that
- e.g. the HTTP module
```
let http = require("http");
```

Method that is called if a browser requests it:
```
let server = http.createServer((req, res) => {
  ...
});
```
- `server` is the variable that handles all the listening
```
server.listen(SERVER_PORT, SERVER_HOSTNAME, (err) => {
  ...
});
```
- if something goes wrong, e.g. something else is already using this port, then the `err` argument is passed and contains some description about the error

Debugging
- set a breakpoint and show how debugging works in VS Code
- do a request in the browser and see that it stops in VS Code

Express
- express is a basic framework for node.js
- it can do network related things like cookies, headers ...

