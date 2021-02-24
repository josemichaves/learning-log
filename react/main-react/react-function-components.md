# React Function Components

A function component is a way to render components via functions.

```jsx
import React from "react";

function App() {
    const greeting = 'Hello world of function components';
    return <h1>{greeting}</h1>
}

export default App;
```

As we can see a function component its basically a class component without the render method in it.

We can also render components inside functions:

```jsx
import React from "react";

function Greeting() {
    const greeting = 'Hello world of function components';
    return <h1>{greeting}</h1>
}

function App() {
    <Greeting />

export default App;
```

One of the main capability of react function components it's that you can pass props to the component itself as it is a function. The props are parameters that are passed down in the components tree.

```jsx
import React from "react";

function App() {
    const greeting = 'Hello world of function components';
    
    return <Headline value={greeting} />
}

function Headline(props) {
        return <h1>{props.value}</h1>
}

export default App;
```

As the props come in object data type we can use destructuring to only obtain what we need.

```jsx
import React from "react";

function App() {
    const greeting = 'Hello world of function components';
    
    return <Headline value={greeting} />
}

function Headline({value}) {
        return <h1>{value}</h1>
}

export default App;
```

