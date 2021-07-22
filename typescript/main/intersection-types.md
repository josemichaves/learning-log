# Intersection Types

An intersection type creates a new type by combining multiple existing types. The new type has all features of the existing types.

You can use the `&` to combine multiple existing types

```typescript
interface BusinessPartner {
    name: string;
    credit: number;
}

interface Identity {
    id: number;
    name: string;
}

interface Contact {
    email: string;
    phone: string;
}

type Employee: Identity & Contact;

const e: Employee = {
    name: 'John',
    id: 423,
    email: 'john@mail.com',
    phone: '+34 329321 312'
}
```

O we can use the separator to tell that this variable could be two types.

```typescript
type Employee = Identity | null

const e: Employee = {
    name: 'John',
    id: 423,
    email: 'john@mail.com',
    phone: '+34 329321 312'
}

const a: Employee
```

