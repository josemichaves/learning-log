# Javascript Generators

Normally a function can return a single value or nothing, but with generators, can return multiples \("yield"\) one after another at demand. 

To creating a generator we need an especial constructor

```javascript
function* generateSequence(){
    yield 1;
    yield 2;
    return 3;
}
```

When a generator its run it doesn't run the function, instead it returns an an object \[object Generator\]

```javascript
function* generateSequence() {
  yield 1;
  yield 2;
  return 3;
}

// "generator function" creates "generator object"
let generator = generateSequence();
alert(generator); // [object Generator]
```

The main method of a generator is `next().` When its called it runs the execution until the nearest `yield` statement. Then the execution pauses and the yielded value it's returned outer the code.

`next()` always return an object with two properties

* `value`: the yielded value
* `done`: `true` if the function code has finished, otherwise `false`

```javascript
function* generateSequence() {
    yield 1;
    yield 2;
    return 3;
}

let generator = generateSequence();

let one = generator.next();
let two = generator.next();
let three = generator.next();
console.log(one) // {value: 1, done:false}
console.log(two) // {value: 2, done:false}
console.log(three) // {value: 3, done:true}
```

We can also iterate over a generator, **the `for...of` ignores the last value because this value is `true`**

```javascript
  function* generateSequence() {
    yield 1;
    yield 2;
    return 3;
}

let generator = generateSequence();

for (let value of generator) {
  console.log(value); //1, then 2
}

// or even we can call the spread operator

let sequence = [0, ...generateSequence()];
console.log(sequence) = 0,1,2,3
```



