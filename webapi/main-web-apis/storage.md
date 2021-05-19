# Storage

The browser lets us to store data in it, we have three ways to store this data Local Storage and Session Storage.

## Local Storage

It's a property that allows us to store data in the window, this data is saved across the browser sessions. In the local storage we can only save strings.

The methods and syntax are the following:

```typescript
localStorage.setItem(key, value) // sets a new entry in the local storage
localStorage.getItem(key) // get the entry with this key
localStorage.removeItem(key) // remove this key
localStorage.clear() // remove all the keys stored in the localstorage
```

## Session Storage

The session storage is the same as the local storage, but with the only difference that this data does not persist, when we close the tab, the session storage will remove these keys.

The methods for the session storage are the same as the Local Storage:

```typescript
sessionStorage.setItem(key, value) // sets a new entry in the local storage
sessionStorage.getItem(key) // get the entry with this key
sessionStorage.removeItem(key) // remove this key
sessionStorage.clear() // remove all the keys stored in the localstorage
```

