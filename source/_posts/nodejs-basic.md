---
title: nodejs-basic
tag: nodejs
category: nodejs
date: 2019-12-04 21:40:29
---
# nodejs
## npm
### package.json
```
{
    "name": "project-name",
    "author": "your name",
    "private": true,
    "dependencies": {},
    "devDependencies": {},
    "scripts": {
        "start": "node app",
    }
}
```
### run scripts
```
$ npm run start
```
### install module
```
# install global: -g
$ npm install {{module-name}} --global
# install local and auto save package.json dependenties.
$ npm install {{module-name}} --save
# install development only
$ npm install {{module-name}} --save-dev
```
### install specific version
```
# install v4
$ npm install lodash@4
# install v4.x.x
$ npm install lodash@^4.0.0
# install v4.17.4
$ npm install lodash@4.17.4
```
## use installed module
```
# use module
var iModule = require("module-name");
```
## user module
### exports
./random_integer.js
```
var MAX = 100;

function randomInteger() {
    return Math.floor(Math.random() * max);
}

module.exports = randomInteger;
//exports only one (function, array, object, string, ...)
```
### use
```
var randomInt = require("./random-integer");
console.log(randomInt());
```
### nodemon
```
# install
$ npm install nodemon --global
# run
$ nodemon index.js
```
### run code by commandline
```
//in browser no require
if (typeof require !== 'undefined' && require.main === module) {
    let parameter = process.argv.slice(2)
}
```