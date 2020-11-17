# JavaScript Higher-Order Functions



Abstraction allows us to write complicated code in a way that’s easy to reuse, debug, and understand for human readers

We can work with functions the same way we would any other type of data including reassigning them to new variables

JavaScript functions are first-class objects, so they have properties and methods like any object

Functions can be passed into other functions as parameters

A higher-order function is a function that either accepts functions as parameters, returns a function, or both.

```javascript
const timeFuncRuntime = funcParameter => {
   let t1 = Date.now();
   funcParameter();
   let t2 = Date.now();
   return t2 - t1;
}
 
const addOneToOne = () => 1 + 1;
 
timeFuncRuntime(addOneToOne);
```

