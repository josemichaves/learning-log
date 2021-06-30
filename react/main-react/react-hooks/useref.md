# useRef\(\)

`useRef(initialValue)` is a built-in React hook that accepts one argument as the initial value and returns a _reference_ \(aka _ref_\). A reference is an object having a special property `current`.

```jsx
function TextInputWithFocusButton() {
  const inputEl = useRef(null);
  const onButtonClick = () => {
    // `current` points to the mounted text input element
    inputEl.current.focus();
  };
  return (
    <>
      <input ref={inputEl} type="text" />
      <button onClick={onButtonClick}>Focus the input</button>
    </>
  );
}
```

`reference.current` accesses the reference value, and `reference.current = newValue` updates the reference value. Pretty simple.

There are 2 rules to remember about references:

1. The value of the reference is _persisted_ \(stays the same\) between component re-renderings;
2. Updating a reference _doesn’t trigger a component re-rendering_.

Now, let’s see how to use `useRef()` in practice.

