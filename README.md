# npmshrink

## Why?

Why not? This semi-useless module is about 15% easier than just chaining together a bunch of scripts in package.json to run `rimraf`, `npm install`, then `npm shrinkwrap`. Although, if this doesn't work for you, you may want to try something far superior, such as [**scripty**](https://www.npmjs.com/package/scripty).

## How?

You can install this garbage globally using something like:

```sh
$ npm i npmshrink -g
```

_OR,_ you can try installing it in your project locally as a devDependency:

```sh
$ npm i npmshrink -D
```

Next, you can use the module by calling one of the following commands (from the Terminal or via an npm script):

1. `npmshrink` &mdash; Alias for `npmshrink:dev` (see below).
1. `npmshrink:dev` &mdash; Deletes the ./node_modules/ directory, installs dependencies and devDependencies from the package.json file and adds them to the generated npm-shrinkwrap.json file.
1. `npmshrink:prod` &mdash; Same as `npmshrink:dev`, but doesn't install the devDependencies from the package.json file (or in the npm-shrinkwrap.json file).

## Example?

Here's a random snippet of a `scripts` block in a package.json file:

```js
  "scripts": {
    "shrink": "npmshrink",
    "shrink:prod": "npmshrink:prod",
    "test": "echo \"Error: no test specified\" && exit 1"
  }
```

In order to [re]generate a shrinkwrap file, you would use one of the two following commands:

1. `$ npm run shrink` &mdash; generates an npm-shrinkwrap.json file with both dependencies _and_ devDependencies.
2. `$ npm run shrink:prod` &mdash; generates an npm-shrinkwrap.json file with _only_ the dependencies (no devDependencies).


## Changelog

* 2.0 - Now runs an expression to convert http:// to https:// in lock files. MPL-2.0 license.
* 1.0 - init release

## License

MPL-2.0
