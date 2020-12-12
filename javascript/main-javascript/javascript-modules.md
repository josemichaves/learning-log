# JavaScript Modules



_Modules_ in Node.js are reusable pieces of code that can be exported from one program and imported for use in another program.



`module.exports` exports the module for use in another program.

```javascript
const myFunc = function () {
    console.log('hello')
}

module.exports = myFunc
```



`require()` imports the module for use in the current program.

```javascript
const myFunc = require('./src.js')
myFunc()

>>>hello
```





ES6 introduced a more flexible, easier syntax to export modules:

default exports use `export default` to export JavaScript objects, functions, and primitive data types.

```javascript
const myFunc = function () {
    console.log('hello')
}

export default myFunc
```



named exports use the `export` keyword to export data in variables.

```javascript
export const myFunc = function () {
    console.log('hello')
}

```



named exports can be aliased with the `as` keyword.

```javascript
const myFunc = function () {
    console.log('hello')
}

export {myFunc as exportedFunction}
```



`import` is a keyword that imports any object, function, or data type.

```javascript
import exportedFunction from './src.js'
exportedFunction()

>>>hello
```

