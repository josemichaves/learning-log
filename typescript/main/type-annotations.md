# Type annotations

## What is Type Annotation in TypeScript

TypeScript uses type annotations to explicitly specify types for identifiers such variables, functions, objects, etc.

TypeScript uses the syntax `: type` after an identifier as the type annotation, where `type` can be any valid type.

Once an identifier is annotated with a type, it can be used as that type only. If the identifier is used as a different type, the TypeScript compiler will issue an error.

### Type annotation in variables and constants

The following syntax shows how to specify type annotations for variables and constants:

```typescript
let variableName: variableType = value
```

Example:

```typescript
let test: string = 'hello';
const test2: number = 'goobdye'
```

In this syntax, the type annotation comes after the variable or constant name and is preceded by a colon \(`:`\).

### Arrays

To annotate an array type you use use a specific type followed by a square bracket `: type[]`

```typescript
let arrayName: type[] = array
```

Example:

```typescript
let names: string[] = ['John', 'Josh', 'Mariah', 'Noah']
```

### Objects

To specify a type for an object, you use the object type annotation. For example:

```typescript
let person : {name: string, age: number} = {
    name: 'John',
    age: 32
};
```

### Function arguments and return types

```typescript
let greeting : (name) => string

const greeting = (name: string) => name;
//Will return the string that we pass

const greeting = (name: string) => console.log(name);
//This will fail beacuse this function expects to return something and this one
// doesn't do that

```



