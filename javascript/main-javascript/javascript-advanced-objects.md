# JavaScript Advanced Objects



The object that a method belongs to is called the _calling object_.



The `this` keyword refers the calling object and can be used to access properties of the calling object. If you want to use a property that is not in the acutal scope, you should use `.this` to be able to use it.

```javascript
var person = {
  firstName: "John",
  lastName : "Doe",
  id       : 5566,
  fullName : function() {
    return this.firstName + " " + this.lastName;
  }
};
```



Methods do not automatically have access to other internal properties of the calling object.

The value of `this` depends on where the `this` is being accessed from.

```javascript
var obj = { a: 'Custom' };

var a = 'Global';

function whatsThis() {
    return this.a;  // The value of this is dependent on how the function is called
}

console.log(whatsThis());          // 'Global' as this in the function isn't set, so it defaults to the global/window object
console.log(whatsThis.call(obj));  // 'Custom' as this in the function is set to obj
```



We cannot use arrow functions as methods if we want to access other internal properties.



JavaScript objects do not have built-in privacy, rather there are conventions to follow to notify other developers about the intent of the code.

The usage of an underscore before a property name means that the original developer did not intend for that property to be directly changed.

```javascript
var person = {
  _firstName: "John",
  _lastName : "Doe",
  _id       : 5566,
  fullName : function() {
    return this.firstName + " " + this.lastName;
  }
};
```



 Setters and getter methods allow for more detailed ways of accessing and assigning properties. They should be declared **inside** the object. When they're called outside the function they don't need the `()`although they seem like a `method`

```javascript
const person = {
    _firstName: "John",
    _lastName: "Doe",
    _id: 5566,
    fullName: function () {
        return this.firstName + " " + this.lastName;
    },

    get firstName() {
        return this._firstName
    },

    set id(newId) {
        this._id = newId;
    }
}

console.log(person.firstName)
person.id = 33442

console.log(person)

>>>John
>>>{
  _firstName: 'John',
  _lastName: 'Doe',
  _id: 33442,
  fullName: [Function: fullName],
  firstName: [Getter],
  id: [Setter]
}
```



Factory functions allow us to create object instances quickly and repeatedly.

```javascript
const Person = function (name, age) {
    this.sayHello = () => console.log('hello!');
    this.name = name;
    this.age = age;
};

const jeff = new Person('jeff', 27);
```



There are different ways to use object destructuring: one way is the property value shorthand and another is destructured assignment.

```javascript
const person = {
    fName: `John`,
    lName: `Snow`,
    location: `Winterfell`,
    nickname: `The Bastard of the Starks`
}

const printInfo = ({ fName, lName, location, nickname }) => {
    console.log(`${fName} ${lName} from ${location}, his nickname is ${nickname}`)
}

printInfo(person)

>>>John Snow from Winterfell, his nickname is The Bastard of the Starks

```

