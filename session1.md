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
```js
let http = require("http");
```

Method that is called if a browser requests it:
```js
let server = http.createServer((req, res) => {
  ...
});
```
- `server` is the variable that handles all the listening
```js
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

## Create a web server

This is called for every request:
```js
let server = http.createServer((req, res) => {
  console.log("Request resolved to url '" + req.url + "'");
});
```
- this will be called for every request
- then your server needs to listen to the requests and do something on them
```js
server.listen(SERVER_PORT, SERVER_HOSTNAME, (err) => {
  ...
});
```
- this is called once in the beginning when you start the server
- as `SERVER_PORT` you can put 3000 or more
- as `SERVER_HOSTNAME` you can put `127.0.0.1`
- do a `console.log()` in the function and call the server to see if it works

## Read a file

Node.js File System Documentation:  
https://nodejs.org/api/fs.html

Task:
- in your `createServer` function, read a file
- be careful: always use async
- if you use sync, this means that all other requests will have to wait until this file reading is done
- explain `fs.readFile()` step by step

```js
let fs = require("fs");
```

```js
fs.readFile('/etc/passwd/', (err, data) => {
  ...
});
```

Callbacks
- node.js works with callbacks, not with promises
- there are libraries that promisify everything, but if you start from scratch, you just have callbacks
- we even use nested callbacks

```js
let server = http.createServer((req, res) => {
  fs.readFile('/public/index.html', (err, data) => {
    if (err) throw err;
    res.statusCode = 200;
    res.setHeader('Content-Type', 'text/html');
    res.end(data);
  });
});
```
- explain step by step
- this is a relative path

## Express

Express JS  
https://expressjs.com/

Install:  
```bash
$ npm install express --save
```

Middleware
- express is based on a middleware
- a middleware is a callback function that is called when a request is made

Deliver static files
- express already has something for that

```js
var express = require('express');
```

```js
app.use(express.static('public'));
```

Task:
- change your index.js so that is uses express
- use express for delivering your files in folder `public`
- have a look at the Hello World example: https://expressjs.com/en/starter/hello-world.html
- get it working with `index.html` and `test.js`

Task:
- take all your files from your travel blog
- put it into `public`
- see if it works
