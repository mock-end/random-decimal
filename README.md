# random-decimal

> Return a random decimal.


[![MIT License](https://img.shields.io/badge/license-MIT_License-green.svg?style=flat-square)](https://github.com/mock-end/random-decimal/blob/master/LICENSE)

[![build:?](https://img.shields.io/travis/mock-end/random-decimal/master.svg?style=flat-square)](https://travis-ci.org/mock-end/random-decimal)
[![coverage:?](https://img.shields.io/coveralls/mock-end/random-decimal/master.svg?style=flat-square)](https://coveralls.io/github/mock-end/random-decimal)


## Install

```
$ npm install --save random-decimal
```

## Usage

```js
var randomDecimal = require('random-decimal');

// API
// - randomDecimal()
// - randomDecimal(options)
```

By default it will return a fixed number of at most 4 digits after the decimal.

```js
randomDecimal();
// default range: 0 to 9007199254740992
// => 211920142886.5024
```

**Note**: *at most* 4 digits. This because, unless we returned trailing zeroes (which aren’t allowed on the JavaScript float) we can’t guarantee 4 digits after the decimal. So if random chance comes back with `82383854.2000` then `82383854.2` is what will be returned.


Can optionally provide min and max:

```js
randomDecimal({max: 5});
// => 2.3785

randomDecimal({min:10, max: 100});
// => 66.7269
```

**Note**: these `min` and `max` are **inclusive**, so they are included in the range.

To retrieve a set number of fixed digits after the decimal, provide it as an option:

```js
randomDecimal({fixed: 7});
// => 749512327.7447168
```

Or combine them:

```js
randomDecimal({min: 0, max: 100, fixed: 8});
// => 45.92367599
```

> For more use-cases see the [tests](https://github.com/mock-end/random-decimal/blob/master/test/spec/index.js)


## Contributing

Pull requests and stars are highly welcome.

For bugs and feature requests, please [create an issue](https://github.com/mock-end/random-decimal/issues/new).
