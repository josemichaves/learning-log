# JavaScript Classes



_Classes_ are templates for objects.



```javascript
class NewClass{
    constructor(param1, param2) {
        this.param1 = _param1;
        this.param2 = _param2;
    }

```

Javascript calls a _constructor_ method when we create a new instance of a class.



_Inheritance_ is when we create a parent class with properties and methods that we can extend to child classes.



```javascript
class NewClass{
    constructor(param1, param2) {
        this.param1 = _param1;
        this.param2 = _param2;
    }
    
class NewSubClass extends NewClass{
    constructor(param3) {
    super(param1);
    this.param3 = _param3;
    
const class1 = new Class(param1, param2);
```

We use the `extends` keyword to create a subclass.

The `super` keyword calls the `constructor()` of a parent class.

With `new Class` we create new instances of the class





```javascript
class NewClass{
    constructor(param1, param2) {
        this.param1 = _param1;
        this.param2 = _param2;
    }
    
static onlyHere(param) {
return 'Only accessible from newClass'
    
class NewSubClass extends NewClass{
    constructor(param3) {
    super(param1);
    this.param3 = _param3;
    

static onlyHere(param) {
    return 'Only accessible from newClass'

    
const class1 = new Class(param1, param2);

console.log(class1._param3)
```

Static methods are called on the class, but not on instances of the class.

