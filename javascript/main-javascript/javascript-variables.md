# JavaScript Variables



Variables hold reusable data in a program and associate it with a name.

Variables are stored in memory.

In pre-ES6 the variables were declarated with `var`

```javascript
var variableName = 'content';
```



`let` is how we declare the variable, this variable can change through the execution of the code.

```javascript
let variableName = 'content'
```



`const` is a another way to declare a variable, in this case the variable content will remain the same through the execution of the code, it will be constant.

```javascript
const variableName = 'content';
```



Variables that have not been initialized store the primitive data type `undefined`.

```javascript
let variableName='';
```



Mathematical assignment operators make it easy to calculate a new value and assign it to the same variable. `+=, -=, *=, /=`

```javascript
let variableName = 1;
console.log(variableName);
>>> 1

variableName += 1;
console.log(variableName);
>>> 2
```



The `+` operator is used to concatenate strings including string values held in variables

```javascript
let variable1 = 'Hello ';
let variable2 = 'World';

console.log(variable1 + variable2);
>>> Hello World
```



We can use backticks ```````` to use a variable inside a string.

```javascript
let variable1 = 'Jhon'

console.log(`Hello ${variable1}, how are you?`);
>>> Hello John, how are you?
```



The `typeof` keyword returns the data type \(as a string\) of a value.

```javascript
const variable1 = 25;
console.log(typeof variable1);
>>> Number
```

