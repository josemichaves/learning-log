# React JSX

JSX is a syntax extension for JavaScript, it's used mainly in React and allows to use HTML mixed with JavaScript.

```jsx
const element = <h1>Hello World</h1>;
```



We can embed JavaScript in the JSX expressions.

We can even embed any type of JavaScript such as operators in the JSX.

We can specify attributes also

```jsx
import React from 'react';
import ReactDOM from 'react-dom';

const person = {
    fName: 'John',
    lName: 'Snow',
    ageBorn: 1985,
    avatar: "johnSnow.jpg"
}

function formatName(person) {
    return person.fName + ' ' + person.lName
}

function knowActualAge(person, actualYear) {
    return actualYear - person.ageBorn
}

const element = (
    <>
        <h1>{formatName(person)}</h1>
        <p>The actual {formatName(person)} age is {knowActualAge(person, 2020)} years old.</p>
        <img src={person.avatar} alt={formatName(person)} />
    </>
)

ReactDOM.render(element, document.getElementById('root'))
```

![](../../.gitbook/assets/screenshot-from-2020-12-12-01-29-00-1-.jpg)

### Some important considerations

When render an element you cannot have more than one outer element, \(ex. two `<p></p>` or `<h1></h1><p></p>`you need something to wrap it in only one element, usually this element is a `<div></div>`or a fragment `<></>`.

A fragment doesn't add any node to the DOM.

When `return`spans over multiple lines you need to wrap it in parenthesis `()`.



