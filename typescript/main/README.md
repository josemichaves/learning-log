# Main

![](../../.gitbook/assets/image%20%2871%29.png)

One of the major problems of JavaScript it's the errors, JavaScript is a programming language that is interpreted and not compiled, this means that the browser in this case is just reading this code and not executing it, so if we have an error in our code this error will show up in the browser but not in the IDE, the other common problem, it's not having the correct data type, for example, if a function expects a number and we pass it a string, this function will fail, because the data type it's not correct, and this error also will show in the browser but not in the IDE, this is where TypeScript appears.

Typescript was created for Microsoft in 2012 as a superset \(a programming language\) written above JavaScript, TypeScript it's a strong typed programming language, in contrast of JavaScript which is a weak typing programming language. The main difference with JavaScript and TypeScript it's that in TS we need to declare the type of every data that we're working it, and TS it's not compatible with the browsers so we need to transpile it in order to execute it in the browser.

```typescript
const functionTest = (param1, param2) => {
    return param1 + param2;
};

functionTest(2, 'hello');
//This will crash when we executed it in the browser
```

```typescript
const functionTest = (param1: number, param2: number) => {
    return param1 + param2;
};

functionTest(2, 'hello');
//Now the code will not execute because the IDE will show an error saying
//hello is not a valid data type for the functionTest function
```

The TypeScript syntax, it's almost the same as JavaScript, but it has some unique attributes that JavaScript doesn't have.

{% page-ref page="type-annotations.md" %}

{% page-ref page="interfaces.md" %}

{% page-ref page="intersection-types.md" %}

{% page-ref page="generics.md" %}

