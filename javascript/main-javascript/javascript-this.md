# JavaScript this

## What is this?

The JavaScript `this` keyword refers to the object it belongs to.

It has a different value depending where it's used:

* In a method, `this` refers to the **owner object**.
* Alone, `this` refers to the **global object**.
* In a function, `this` refers to the **global object**.
* In a function, in strict mode, `this` is `undefined`.
* In an event, `this` refers to the **element** that received the event.

## **Method**

In an object method, this refers to the "owner" of the method.

In the example on the top of this page, this refers to the person object.

The person object is the owner of the fullName method.

```javascript
const person = {
  firstName: "John",
  lastName: "Doe",
  id: 5566,
  fullName : function() {
    return this.firstName + " " + this.lastName;
  }
```

## Alone

When used alone, the **owner** is the Global object, so `this` refers to the Global object.

In a browser window the Global object is `[object Window]`:

```javascript
const x = this;
```

## Function

In a JavaScript function, the owner of the function is the **default** binding for `this`.

So, in a function, `this` refers to the Global object `[object Window]`.

```javascript
const myFn = () => this;
```

JavaScript **strict mode** does not allow default binding.

So, when used in a function, in strict mode, `this` is `undefined`.

## Event handlers

In HTML event handlers, `this` refers to the HTML element that received the event:

```markup
<button onclick="this.style.display='none'">
  Click to Remove Me!
</button>
```



