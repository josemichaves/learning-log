# Javascript Conditionals



```javascript
let name = 'Mick';

if (name === 'John'){
    console.log('Hello John!');
} else if (name === 'Mick') {
    console.log('Hello Mick!');
} else {
    console.log('I don\'t know who you are');
}

>>> Hello Mick!
```

An `if` statement checks a condition and will execute a task if that condition evaluates to `true`.

`if...else` statements make binary decisions and execute different code blocks based on a provided condition.

We can add more conditions using `else if` statements.



```javascript
let name = 'mick';
let age = 10;

if (age => 18) {
    console.log('You\'re an adult');
} else if (age < 18) {
    console.log('You\'re not an adult yet')
    }

>>>You're not an adult yet
```

Comparison operators, including `<`, `>`, `<=`, `>=`, `===`, and `!==` can compare two values.



```javascript
let name = '';
let age = 10;

if (age === 10) && (name === 'mick') {
    console.log('Your name is Mick and you are 10 years old');
} else if (age === 10) || (name === '') {
    console.log('You\'re 10 years old, but i don\'t know your name');
}

>>> You're 10 years old, but i don't know your name
```

The logical and operator, `&&`, or “and”, checks if both provided expressions are truthy.

The logical operator `||`, or “or”, checks if either provided expression is truthy.



```javascript
let name = 'Mick';

if (!name) {
 console.log('Your name is not Mick');
} else {
  console.log('Maybe your name is mick');
} 

>>> Maybe your name is mick
```

The `!`, switches the truthiness and falsiness of a value. Logical NOT operator.



```javascript
let name='mick'

if (name==='mick') ? console.log('You\'re mick!') : console.log('You\'re not mick!');

>>> You're mick!

```

The ternary operator is shorthand to simplify concise `if...else` statements.

let day='5';

switch \(day\) { case '0': day='Monday'; break; case '1': day='Thursday'; break; case '2': day='Wednesday'; break; default: day='Don\'t know what day is' }

console.log\(day\)

```javascript
let day=2

switch (day) {
case 0:
    day='Monday';
    break;
case 1:
    day='Thursday';
    break;
case 2:
    day='Wednesday';
    break;
default:
    day='Don\'t know what day is it';
}


console.log(day)

>>> Wednesday


```

A `switch` statement can be used to simplify the process of writing multiple `else if` statements. The `break` keyword stops the remaining `case`s from being checked and executed in a `switch` statement.

