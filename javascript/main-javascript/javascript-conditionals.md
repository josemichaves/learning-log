# Javascript Conditionals



An `if` statement checks a condition and will execute a task if that condition evaluates to `true`.

`if...else` statements make binary decisions and execute different code blocks based on a provided condition.

We can add more conditions using `else if` statements.

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

Comparison operators, including `<`, `>`, `<=`, `>=`, `===`, and `!==` can compare two values.

The logical and operator, `&&`, or “and”, checks if both provided expressions are truthy.

The logical operator `||`, or “or”, checks if either provided expression is truthy.

The bang operator, `!`, switches the truthiness and falsiness of a value.

The ternary operator is shorthand to simplify concise `if...else` statements.

A `switch` statement can be used to simplify the process of writing multiple `else if` statements. The `break` keyword stops the remaining `case`s from being checked and executed in a `switch` statement.

