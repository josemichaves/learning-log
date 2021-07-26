# Type Coercion

Type coercion is the automatic or implicit conversion of values from one data type to another \(such as strings to numbers\).

```typescript
const value1 = '5';
const value2 = 9;
let sum = value1 + value2;

console.log(sum);
/// 14
```

Here at first sight this will throw an error, because we're adding a string to a number, or even we could obtain 59, but what we have is the result of the sum, that's because the type coercion, in this case JavaScript has converted the type of `value1` to a number in order to add them to the `value2.`



