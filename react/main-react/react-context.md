# React Context

## What is context and how to use it?

A React context is a state that persists along all the tree of React components, and let us to interact with this state even if we're not declaring this in the component.

First of all we need to declare the context.

```typescript
const MyContext = React.createContext(defaultValue);
```

Here we're creating the context, and assigning a default value to it, this property will be accessible via the `useContext(ContextName)`.

Once we've created the context, we can export this value with the `Provider` component.

```typescript
<MyContext.Provider value={someValue}>
```

And finally we need to wrap all of our components \(generally in App.js\) with our context provider.

```typescript
<MyContext.Provider>
    <Component1 />
    <Component2 />
    <Component3 />
</MyContext.Provider>
```

As we can see the context accepts children so the follow context will be something like this.

```typescript
const UserContext = React.createContext(null)

export const UserProvider = ({children}) => {
  const [user, setUser] = useState(null);
  const changeuser = (name, surname) => {
    setUser({ name: name, surname: surname });
  };
  return (
    <UserContext.Provider value={{ user, changeUser }}>
      {children}
    </UserContext.Provider>
  );
};
```

And then wrap the whole app in the context.

```typescript
<UserContext.Provider>
    <Component1 />
    <Component2 />
    <Component3 />
</UserContext.Provider>
```

And finally we can access to these properties in whatever component of our React App.

```typescript
const { user, changeUser } = useContext(UserContext);

console.log(`Actual user is ${user}`);
// null

changeUser("John", "Snow");

console.log(`Actual user is ${user}`);
// {name: 'John', surname: 'Snow}
```

As we can see we can pass whatever we need in the context, such a state for defining a user, or a setter to set a new user.

## When to use Context?

Context is mainly used when the data that we want to share is needed by a lot of components, using the context, we can avoid passing the props too deep into the components, with the context we only declare once, and all the components that are wrapped will have this property accessible.

If we only need to share this data in one component, or even two, is better to pass the data down as a prop.

Because context sometimes complicates the way that we share data on the most top levels, and forces us to build a very flexible bottom component.

