# use [![NPM version](https://badge.fury.io/js/use.svg)](http://badge.fury.io/js/use)

> Easily add plugin support to your node.js application.

## Install

Install with [npm](https://www.npmjs.com/)

```sh
$ npm i use --save
```

## Usage

```js
var use = require('use');
```

## API

### [.use](index.js#L49)

Define a plugin function to be passed to use. The only parameter exposed to the plugin is the application instance.

Also, if a plugin returns a function, the function will be pushed
onto the `fns` array, allowing the plugin to be called at a
later point, elsewhere in the application.

**Params**

* `fn` **{Function}**: plugin function to call
* `returns` **{Object}**: Returns the item instance for chaining.

**Example**

```js
var use = require('use');

// define a plugin
function foo(app) {
  // do stuff
}

var app = function(){};
use(app);

// register plugins
app.use(foo);
app.use(bar);
app.use(baz);
```

### [.run](index.js#L65)

Run all plugins on `fns`. Any plugin that returns a function when called by `use` is pushed onto the `fns` array.

**Params**

* `value` **{Object}**: Object to be modified by plugins.
* `returns` **{Object}**: Returns the item instance for chaining.

**Example**

```js
var config = {};
app.run(config);
```

## Similar projects

* [base-methods](https://www.npmjs.com/package/base-methods): Starter for creating a node.js application with a handful of common methods, like `set`, `get`,… [more](https://www.npmjs.com/package/base-methods) | [homepage](https://github.com/jonschlinkert/base-methods)
* [ware](https://www.npmjs.com/package/ware): Easily create your own middleware layer. | [homepage](https://github.com/segmentio/ware)

## Running tests

Install dev dependencies:

```sh
$ npm i -d && npm test
```

## Contributing

Pull requests and stars are always welcome. For bugs and feature requests, [please create an issue](https://github.com/jonschlinkert/use/issues/new).

## Author

**Jon Schlinkert**

+ [github/jonschlinkert](https://github.com/jonschlinkert)
+ [twitter/jonschlinkert](http://twitter.com/jonschlinkert)

## License

Copyright © 2015 Jon Schlinkert
Released under the MIT license.

***

_This file was generated by [verb-cli](https://github.com/assemble/verb-cli) on November 10, 2015._