# esdoc-node

[![](https://travis-ci.org/ddude/esdoc-node.svg)](https://travis-ci.org/ddude/esdoc-node)

## Usage

Get the package:

``` shell
npm install esdoc-node
```

Add the following to your esdoc config file:

``` json
{
  "plugins": [{"name": "esdoc-node"}]
}
```

## What it does

It converts the input of esdoc so that node.js' `exports` and
`module.exports` becomes ES6's `export`.

This table shows the translation rules:

| Before                                    | After                            |
|-------------------------------------------|----------------------------------|
|`module.exports = ...;`                    |`export default ...;`             |
|`exports.Hello = class Hello { ... };`     |`export class Hello { ... };`     |
|`exports.world = function world() { ... };`|`export function world() { ... };`|
|`exports.value = value;`                   |`export { value };`               |
|`exports.value = ...;`                     |`export let value = ...;`         |
