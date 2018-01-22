# bind-deep
[![npm version](https://img.shields.io/npm/v/bind-deep.svg)](https://www.npmjs.com/package/bind-deep)
[![Travis](https://img.shields.io/travis/danielhickman/bind-deep.svg)](https://travis-ci.org/danielhickman/bind-deep)
[![license](https://img.shields.io/github/license/danielhickman/bind-deep.svg)](/LICENSE)

## Description
Bind an object to `this` in all methods in a function or object. Simple, dependency-free alternative to [deep-bind](https://github.com/jonschlinkert/deep-bind).


## Installation
###### From npm
```bash
$ npm install bind-deep
```
###### As a dependency
```bash
# Create package.json for your own module if you haven't already
$ npm init

# Install bind-deep and add to dependencies
$ npm install bind-deep --save
```
###### From source
```bash
$ git clone https://github.com/danielhickman/bind-deep
$ cd bind-deep/
$ npm install
```


---


## Usage
```js
// Require bind-deep
const bindDeep = require("bind-deep");


// Original object and function
// Could also be an actual object
const func = function() {
	// Use `this`
};
func.method = function() {
	// Use `this` again
};

const obj = {
	method() {
		// Use `this`
	}
};


// Deeply bound object and function
// `thisArg` will be what every function and method will see as `this`
const boundObj = bindDeep(thisArg, obj);
// => {method: [Function: bound]}

const boundFunc = bindDeep(thisArg, func);
// => {[Function: bound] method: [Function: bound]}
```


## License
Copyright Daniel Hickman, [MIT License](https://github.com/danielhickman/bind-deep/blob/master/LICENSE)
