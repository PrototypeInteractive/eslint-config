# @prototype-interactive/eslint-config

[![NPM version][npm-image]][npm-url] [![Downloads][downloads-image]][npm-url] [![Build Status][travis-image]][travis-url] [![Coverage Status][codecov-image]][codecov-url] [![Dependency status][david-dm-image]][david-dm-url] [![Dev Dependency status][david-dm-dev-image]][david-dm-dev-url]


[npm-url]:https://npmjs.org/package/@prototype-interactive/eslint-config
[npm-image]:http://img.shields.io/npm/v/@prototype-interactive/eslint-config.svg
[downloads-image]:http://img.shields.io/npm/dm/@prototype-interactive/eslint-config.svg
[travis-url]:https://travis-ci.org/PrototypeInteractive/eslint-config
[travis-image]:http://img.shields.io/travis/PrototypeInteractive/eslint-config/master.svg
[codecov-url]:https://codecov.io/gh/PrototypeInteractive/eslint-config
[codecov-image]:https://img.shields.io/codecov/c/github/PrototypeInteractive/eslint-config/master.svg
[david-dm-url]:https://david-dm.org/PrototypeInteractive/eslint-config
[david-dm-image]:https://img.shields.io/david/PrototypeInteractive/eslint-config.svg
[david-dm-dev-url]:https://david-dm.org/PrototypeInteractive/eslint-config?type=dev
[david-dm-dev-image]:https://img.shields.io/david/dev/PrototypeInteractive/eslint-config.svg

Prototype Interactive [eslint](http://eslint.org/) configuration to be used across several JavaScript projects.

_Originaly based off [MOXY](https://github.com/moxystudio/eslint-config-moxy)'s._


## Installation

`$ npm install --save-dev eslint @prototype-interactive/eslint-config`

## Usage

Create a `.eslintrc.json` file in the project root using a base configuration and addons.

First you need to choose the **base** configuration to use:

- `es5` - The configuration to be used in ECMAScript 5 based projects
- `es6` - The configuration to be used in ECMAScript 6 based projects (aka 2015)
- `es7` - The configuration to be used in ECMAScript 7 based projects (aka 2016)
- `es8` - The configuration to be used in ECMAScript 8 based projects (aka 2017)
- `es9` - The configuration to be used in ECMAScript 9 based projects (aka 2018)

Then enhance it with one or more **addons**:

- `browser` - If you are going to develop code for the browser (assumes you use CommonJS or AMD)
- `node` - If you are going to develop code for [NodeJS](nodejs.org)
- `es-modules`: If you are going to use ES6 import & export instead of CommonJS or AMD
- `babel-parser`: Use [babel-eslint](https://github.com/babel/babel-eslint) parser so that you may use language features that are not yet implemented in eslint (e.g.: dynamic imports)
- `react` - If you are going to use [React](https://reactjs.org/) (requires `es6` base configuration or higher)
- `jest` - If you are going to use [Jest](https://facebook.github.io/jest/) to develop tests


### Examples

Cutting edge React in the browser:

```json
{
    "root": true,
    "extends": [
        "@prototype-interactive/eslint-config/es9",
        "@prototype-interactive/eslint-config/addons/browser",
        "@prototype-interactive/eslint-config/addons/es-modules",
        "@prototype-interactive/eslint-config/addons/react"
    ]
}
```

Cutting edge NodeJS:

```json
{
    "root": true,
    "extends": [
        "@prototype-interactive/eslint-config/es9",
        "@prototype-interactive/eslint-config/addons/node"
    ]
}
```

Cutting edge NodeJS with ES modules (requires a transpiler such as Babel or similar):

```json
{
    "root": true,
    "extends": [
        "@prototype-interactive/eslint-config/es9",
        "@prototype-interactive/eslint-config/addons/node",
        "@prototype-interactive/eslint-config/addons/es-modules"
    ]
}
```

Old ES5 in the browser:

```json
{
    "root": true,
    "extends": [
        "@prototype-interactive/eslint-config/es5",
        "@prototype-interactive/eslint-config/addons/browser"
    ]
}
```

Note that by setting `root` to true, we ensure that no ancestor configuration is used which also improves `ESLint` performance because no more file lookups need to be done.


## Tests

`$ npm test`
`$ npm test -- --watch` during development


## License

[MIT License](http://opensource.org/licenses/MIT)
