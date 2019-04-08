## 1.4.5

Fixes for Angular 6+ applications using compiled Dart package w/ preamble:

* Checks for global if it's not polyfilled, then try for window.
* Don't assume that since we have CommonJS we have process, __dirname, __filename.

## 1.4.4

* Explicitly support Dart 2 stable releases.

## 1.4.3

* Add Node detector for Browserify/Webpack-type environments. (thanks to @lexaknyazev for reporting!)
* Add examples for pub (thanks @bcko!)

## 1.4.2

* Keep `Uri.base` up to date when the current working directory changes.
* Add .dart_tool to gitignore. 

## 1.4.1

* Make sure to replace all backslashes for cwd on Windows, not just the first.

## 1.4.0

* Add __dirname and __filename to exposed globals. Adds ability of exposing more
  globals in the preamble by calling `getPreamble(additionalGlobals: ["__dirname", ...])`.

## 1.3.0

* Add minified versions of the preamble accessible as `lib/preamble.min.js` and
  by calling `getPreamble(minified: true)`.

## 1.2.0

* Prevent encapsulation, `global.self = global` (old) vs.
  `var self = Object.create(global)` (new).

## 1.1.0

* Set `global.location` so that `Uri.base()` works properly on Windows in most
  cases.

* Define `global.exports` so that it's visible to the compiled JS.
