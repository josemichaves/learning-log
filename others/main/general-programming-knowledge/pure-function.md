# Pure Function

A pure function is a function which:

* Given the same input, will always return the same output.
* Produces no side effects.

Pure functions have many beneficial properties, and form the foundation of functional programming. Pure functions are completely independent of outside state, and as such, they are immune to entire classes of bugs that have to do with shared mutable state. Their independent nature also makes them great candidates for parallel processing across many CPUs, and across entire distributed computing clusters, which makes them essential for many types of scientific and resource-intensive computing tasks.

For example this function is not pure because never return the same value:

```typescript
Math.random() //0.51465145147
Math.random() //0.1487814234
Math.random() //0.7893515457
```

A function is only pure if, given the same input, it will always produce the same output:

```typescript
const highpass = (cutoff, value) => value >= cutoff;

highpass(5, 5); // => true
highpass(5, 5); // => true
highpass(5, 5); // => true
```

In this case we can see is pure because the output is consistent.

```typescript
highpass(5, 123); // true
highpass(5, 6);   // true
highpass(5, 18);  // true
highpass(5, 1);   // false
highpass(5, 3);   // false
highpass(5, 4);   // false
```

Even with other data the result keeps the same.

A pure function produces no side effects, which means that it can’t alter any external state.



