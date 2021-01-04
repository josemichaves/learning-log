# React Hooks

Hooks are a built-in functions that let us use state and lifecylce methods inside a functional components,   

```jsx
import React from "react"
import { useState} from "react"

function example() {
const [count, setCount] = useState(0)

return (
    <div>
        <p> You clicked {count} times </p>
        <button onClick={() => setCount(count + 1)}>
            Click Me
        </button>
    </div>
);
}
```

