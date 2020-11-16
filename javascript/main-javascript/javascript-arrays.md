# JavaScript Arrays



Arrays are lists that store data in JavaScript.

Arrays are created with brackets `[]`.

```javascript
let myArray = [arrayItem1, arrayItem2, arrayItem3, ...];
```



Each item inside of an array is at a numbered position, or index, starting at `0`.

We can access one item in an array using its index, with syntax like: `myArray[0]`.

```javascript
let myArray = [arrayItem1, arrayItem2, arrayItem3];
console.log(myArray[2];
>>>'arrayItem3'
```



We can also change an item in an array using its index, with syntax like `myArray[0] = 'new string'`;

```javascript
const myArray = [arrayItem1, arrayItem2, arrayItem3];
myArray[1] = 'newArrayItem';

console.log(myArray);
>>> [arrayItem1, newArrayItem, arrayItem3]
```



Arrays have a `length` property, which allows you to see how many items are in an array.

```javascript
const myArray = [arrayItem1, arrayItem2, arrayItem3];
console.log(myArray.length);

>>> 3
```



Arrays have their own methods, including `.push()` and `.pop()`, which add and remove items from an array, respectively.

```javascript
const myArray = [arrayItem1, arrayItem2, arrayItem3];
myArray.push['arrayItem4];
console.log(myArray)
>>>[arrayItem1, arrayItem2, arrayItem3, arrayItem4]

myArray.pop();
console.log(myArray);
>>>[arrayItem1, arrayItem2, arrayItem3]

```



Some built-in methods are mutating, meaning the method will change the array, while others are not mutating. You can always check the documentation.

Arrays mutated inside of a function will keep that change even outside the function

Variables that contain arrays can be declared with `let` or `const`. Even when declared with `const`, arrays are still mutable. However, a variable declared with `const` cannot be reassigned.

```javascript
const myArray = [arrayItem1, arrayItem2, arrayItem3];

myArray = [newArraysItems];
ERROR!

myArray [2] = newArrayItem;
console.log(myArray);
>>>[arrayItem1, newArrayItem, arrayItem3];


let myArray = [arrayItem1, arrayItem2, arrayItem3];
myArray = [newArrayItems};
console.log(myArray);
>>>[myArray]
```



Arrays can be nested inside other arrays.

```javascript
myNestedArray = [mainArray[childArray1,childArray2]
```



To access elements in nested arrays chain indices using bracket notation.

```javascript
myNestedArray = [array1[childArray1,childArray2],array2[childArray3,childArray4];
console.log(mainArray[1][0];
>>>[childArray3]
```

