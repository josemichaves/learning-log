# Interfaces

Interfaces are one of the superpowers of TypeScript.

TypeScript interfaces define the contracts within your code. They also provide explicit names for type checking.

```typescript
const getFullName (person: {firstname: string, lastName: string}) => {
    return `${person.firstname}, ${person.lastname};
};
```

There's nothing wrong with this function, we're declaring the datatypes at it's should, but TypeScript let us to reuse that type annotations to use it in other function that will accept the same data, these are called the Interfaces.

```typescript
interface Person {
    firstname: string;
    lastname: string;
};

const getFullName (person: Person) => {
    return `${person.firstname}, ${person.lastname}
};
```

This two examples works in the same way, but the second example is more clear and reusable what data it's accepting.



