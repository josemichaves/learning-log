# Functional Programing

## What is functional programing?

**Functional programming** \(often abbreviated FP\) is the process of building software by composing **pure functions**, avoiding **shared state,** **mutable data,** and **side-effects**. Functional programming is **declarative** rather than **imperative**, and application state flows through pure functions. Contrast with object oriented programming, where application state is usually shared and colocated with methods in objects. Functional programing is a paradigm.

## Pure functions

A **pure function** is a function which:

* Given the same inputs, always returns the same output, and
* Has no side-effects

## Shared state

**Shared state** is any variable, object, or memory space that exists in a shared scope, or as the property of an object being passed between scopes. A shared scope can include global scope or closure scopes. Often, in object oriented programming, objects are shared between scopes by adding properties to other objects.

The problem with shared state is that in order to understand the effects of a function, you have to know the entire history of every shared variable that the function uses or affects.

## Mutable data

An immutable object is an object that can’t be modified after it’s created. Conversely, a mutable object is any object which can be modified after it’s created.

Immutability is a central concept of functional programming because without it, the data flow in your program is lossy.

## Side effects

A side effect is any application state change that is observable outside the called function other than its return value. Side effects include:

* Modifying any external variable or object property \(e.g., a global variable, or a variable in the parent function scope chain\)
* Logging to the console
* Writing to the screen
* Writing to a file
* Writing to the network
* Triggering any external process
* Calling any other functions with side-effects

Side effects are mostly avoided in functional programming, which makes the effects of a program much easier to understand, and much easier to test.



