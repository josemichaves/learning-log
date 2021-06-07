# Babel Js

Babel is a JavaScript transpiler that converts any specification of JavaScript to ES5, the old specification that can run in every browser.

For example, in ES5 the classes did not exist, but if nowadays you want to use the classes you can, and BabelJs will transpile this code in the ES5 specification

```javascript
class Person {}
const John = new Person
```

When we apply BabelJs to this code it will turn into something like that.

```javascript
"use strict";
function _classCallCheck(instance, Constructor) {
  if (!(instance instanceof Constructor)) {
    throw new TypeError("Cannot call a class as a function");
  }
}
var Person = function Person() {
  _classCallCheck(this, Person);
};
var dave = new Person();
```

The two codes works exactly the same, but they're written in differents specifications, the one that generate BabelJs will run in almost every browser and version of it, while the newest specification code may not run in olders browser. Thats why using BabelJs is important to make this code usable in all the browsers.

In order to use BabelJs we can install it as an [npm package](https://www.npmjs.com/package/@babel/cli) and start transpiling code.

