# Generics

A generic allows us to create a function without specifying what datatype the parameters will be at the time of creation, but when we call this function we'll need to specify the datatype that we're sending it.

```typescript
function getRandomElement<T>(items: T[]): T {
    let randomIndex = Math.floor(Math.random() * items.length);
    return items[randomIndex];
}

let numbers = [1, 5, 7, 4, 2, 9];
let randomEle = getRandomElement(numbers); 
console.log(randomEle);
```

