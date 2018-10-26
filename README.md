# Changes to the workshop that I did:

* Babel docs: https://babeljs.io/docs/en/

## Setup:

* Package changes:
* `babel` -> `@babel/core`
* `babel-preset-env` -> `@babel/preset-env`
* `babel-preset-react` -> `@babel/preset-react`
* `babel-preset-stage-2` -> See: https://babeljs.io/docs/en/babel-preset-stage-2

### In the terminal:

* `npm install --save-dev @babel/core babel-loader @babel/preset-env @babel/preset-react`
* `npm install --save @babel/polyfill` (this allows async/await in client)
* Install desired stage-2 and stage-3 plugins.
* (I've only needed to use `npm install --save-dev @babel/plugin-proposal-class-properties`)

### .babelrc:

* Change presets. (Add plugins as needed).

```
{
  "presets": ["@babel/react", "@babel/env"],
  "plugins": [
    ["@babel/plugin-proposal-class-properties", { "loose": false }]
  ]
}
```

### webpack.config.js:

* If you installed `@babel/polyfill`, change the `entry` option.

```
module.exports = {
  entry: ['@babel/polyfill', './index.js'],
  // rest of file
}
```
