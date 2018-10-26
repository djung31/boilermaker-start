# Changes to the workshop that I did:

* Babel docs: https://babeljs.io/docs/en/

## Setup:

Package changes:
* `babel` -> `@babel/core`
* `babel-preset-env` -> `@babel/preset-env`
* `babel-preset-react` -> `@babel/preset-react`
* `babel-preset-stage-2` -> Didn't use. See: https://babeljs.io/docs/en/babel-preset-stage-2

New package:
* `@babel/polyfill` (allows async/await in client)

### In the terminal:

* `npm install --save-dev @babel/core babel-loader @babel/preset-env @babel/preset-react`
* `npm install --save @babel/polyfill`
* Install desired stage-2 and stage-3 plugins with `npm install --save-dev` as needed.
* (I think I only needed `@babel/plugin-proposal-class-properties`, for arrow funcs in classes)

### .babelrc:

* Update presets. (Add plugins as needed).

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
  entry: ['@babel/polyfill', './path/to/starter/file.js'],
  // rest of file
}
```
