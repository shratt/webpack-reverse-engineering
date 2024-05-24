# Chunk Format
**NOTE: the webpacks name is NOT always webpackJsonp, i expect you to know that if you are reading this.**

- checks if webpack runtime exists and if not it defines webpackJsonp as an empty array <br>
`(window.webpackJsonp = window.webpackJsonp || [])`
- `.push()` into that an array containing:
  - an array containing the chunk ID (eg. `[1234]`),
  - an object containing the modules it is pushing in the chunk
  - runtime function/array (will be documented later)
## example chunk
```js
  (window.webpackJsonp = window.webpackJsonp || []).push([[1234],
    {
      1: function (module, exports, require) { 
          module.exports = "Hello World!";
      },
      2: function (module, exports, require) { 
          console.log(require(1));
      },
    }]);
```
