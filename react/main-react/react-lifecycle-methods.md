# React Lifecycle Methods

The components life in React has three high level parts:

1. **Mounting** : When the component is being initialized and rendered for the first time.
2. **Updating**: When the component updates due to state or props changes.
3. **Unmounting**: When the component is being removed from the DOM.

When we call a call a method in the Mounting phase we have an order

1. The constructor
2. `render()`
3. `componentDidMount()`

The `componentDidMount()` is used when the component is being initialized

The method `componentWillUnmount()` it's called tight before the component it's completely removed from the DOM, usually this is made to remove all the server side-effect that the component can had.

The `componentDidUpdate()` it's called when we want to update a component, it's called in the updating phase.



