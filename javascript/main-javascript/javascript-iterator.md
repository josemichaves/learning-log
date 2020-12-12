# JavaScript Iterator

`.forEach()` is used to execute the same code on every element in an array but does not change the array and returns `undefined`.

```javascript
const arraySparse = [1,3,,7]
let numCallbackRuns = 0

arraySparse.forEach((element) => {
  console.log(element)
  numCallbackRuns++
})

console.log("numCallbackRuns: ", numCallbackRuns)

>>> 1
>>> 3
>>> 7
>>>numCallbackRuns: 3

```



`.map()` executes the same code on every element in an array and returns a new array with the updated elements.

```javascript
let numbers = [1, 4, 9]
let roots = numbers.map(function(num) {
    return Math.sqrt(num)
})

---roots is now     [1, 2, 3]
---numbers is still [1, 4, 9]
```



`.filter()` checks every element in an array to see if it meets certain criteria and returns a new array with the elements that return truthy for the criteria.

```javascript
function isBigEnough(value) {
  return value >= 10
}

let filtered = [12, 5, 8, 130, 44].filter(isBigEnough)
---filtered is [12, 130, 44]
```



`.findIndex()` returns the index of the first element of an array which satisfies a condition in the callback function. It returns `-1` if none of the elements in the array satisfies the condition.

```javascript
function isPrime(num) {
  for (let i = 2; num > i; i++) {
    if (num % i == 0) {
      return false;
    }
  }
  return num > 1;
}

console.log([4, 6, 8, 9, 12].findIndex(isPrime)); 
console.log([4, 6, 7, 9, 12].findIndex(isPrime)); 
>>> -1, not found
>>> 2 (array[2] is 7)
```



`.reduce()` iterates through an array and takes the values of the elements and returns a single value.

```javascript
let sum = [0, 1, 2, 3].reduce(function (accumulator, currentValue) {
  return accumulator + currentValue
}, 0)
---sum is 6

```



All iterator methods takes a callback function that can be pre-defined, or a function expression, or an arrow function.

