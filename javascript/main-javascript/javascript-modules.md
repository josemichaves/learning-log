# JavaScript Modules



_Modules_ in Node.js are reusable pieces of code that can be exported from one program and imported for use in another program.



```javascript
const myFunc = function () {
    console.log('hello')
}

module.exports = myFunc
```

`module.exports` exports the module for use in another program.



```javascript
const myFunc = require('./src.js')
myFunc()

>>>hello
```

`require()` imports the module for use in the current program.





ES6 introduced a more flexible, easier syntax to export modules:

```javascript
const myFunc = function () {
    console.log('hello')
}

export default myFunc
```

default exports use `export default` to export JavaScript objects, functions, and primitive data types.



```javascript
export const myFunc = function () {
    console.log('hello')
}

```

named exports use the `export` keyword to export data in variables.



```javascript
const myFunc = function () {
    console.log('hello')
}

export {myFunc as exportedFunction}
```

named exports can be aliased with the `as` keyword.



```javascript
import exportedFunction from './src.js'
exportedFunction()

>>>hello
```

`import` is a keyword that imports any object, function, or data type.

