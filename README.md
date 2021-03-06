# babel-plugin-version-transform
Replaces keyword `VERSION` with a stringified copy of the package.json version number.

## Example

###### Given this package.json
```json
{
  "version": "1.0.0"
}
```

### In

```js
function log(data) {
  xhr({...data, version: VERSION});
}
```

### Out

```js
function log(data) {
  xhr({...data, version: "1.0.0"});
}
```

## Installation

```sh
$ npm install babel-plugin-version-transform
```

## Usage

### Via `.babelrc` (Recommended)

**.babelrc**

```json
{
  "plugins": [
    "version-transform"
  ]
}
```

### Via CLI

```sh
$ babel --plugins version-transform script.js
```

### Via Node API

```javascript
require("babel-core").transform("code", {
  plugins: ["version-transform"],
});
```
