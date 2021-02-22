# React Hooks

Hooks are a built-in functions that let us use state and lifecylce methods inside a functional components.

The two most used hooks are: `useState` and   `useEffect`

## useState\(\)

`useState` holds an state, we can give this state to a variable, and the state will update. It's a way to preserve a value between the function calls.

When declaring a `useState` hook we first need to give it a parametter, this parameter will be the initial state that will hold. We need to specify also the state name, and the setter for the state.

Then we can view the state, or update with the setter.

```jsx
import React, {useState} from "react"

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

## useEffect

The hook `useEffect`  let us execute when a component mounts/unmounts, when we update a state, basically when something happens, they're calle side-effects, when a component makes a side-effect\(updating a state\) we can call the `useEffect` to perform a task.

We can pass an array, to tell the hook, when it needs to be executed, because if not, it will execute every time, something renders.

```jsx
import React, {useState, useEffect} from "react;

function example(){
    const count, setCount] = useState(0)

    useEffect (() => {
        return document.title = {count}
    }, [count])
    
```

## Other hooks

There're a lot of pre-built hooks:

* `useContext`
* `useReducer`
* `useCallback`
* `useMemo`
* `useRef`
* `useImperativeHandle`
* `useLayoutEffect`
* `useDebugValue`

You can even create custom hooks by yourself

## Rules of Hooks

There're two rules of hooks:

### Only call hooks at top level

You cannot call hooks inside loops, conditions or nested functions.

### **Hooks can only be called inside react functions.**

