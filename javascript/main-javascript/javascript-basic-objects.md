# JavaScript Basic Objects



```javascript
object = {
    key: value,
    key2: value2
};
```

Objects store collections of _key-value_ pairs.



```javascript
object = {
    key: value,
    key2: method = () => {
        console.log("I'm a method");
    }
};
```

Each key-value pair is a property—when a property is a function it is known as a method.



```javascript
object = {
    key: "value",
    key2: {
        "sub Key1": "subValue1",
        subKey2: "subValue2"
    }
}
```

An object literal is composed of comma-separated key-value pairs surrounded by curly braces. An object literal is an object inside another object



```javascript
object = {
    key: "value",
    key2: {
        "sub Key1": "subValue1",
        subKey2: "subValue2"
    }
}

object.key3 = "value 3";
object.key2["sub Key1"] = "subValue3"

console.log(object)

>>>{
      key: 'value',
      key2: { subKey1: 'subValue3', subKey2: 'subValue2' },
      key3: 'value 3'
}
```

You can access, add or edit a property within an object by using dot notation or bracket notation.





```javascript
object = {
    key: function () {
        var x = "Hello!!";
        return x
    },
    key2: {
        "sub Key1": "subValue1",
        subKey2: "subValue2"
    }
}

```

* We can add methods to our object literals using key-value syntax with anonymous function expressions as values or by using the new ES6 method syntax.
* We can navigate complex, nested objects by chaining operators.
* Objects are mutable—we can change their properties even when they’re declared with `const`.
* Objects are passed by reference— when we make changes to an object passed into a function, those changes are permanent.
* We can iterate through objects using the `For...in` syntax.

