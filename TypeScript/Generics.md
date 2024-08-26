### Generics

![TypeScript Logo](https://www.typescriptlang.org/assets/images/icons/favicon-32x32.png)

[TypeScript Documentation](https://www.typescriptlang.org/docs/)

## Index
1. [What are Generics?](#what-are-generics)
2. [Generic Functions](#generic-functions)
3. [Generic Interfaces](#generic-interfaces)
4. [Generic Classes](#generic-classes)
5. [Constraints in Generics](#constraints-in-generics)
6. [Example: Using Generics in a Utility Function](#example-using-generics-in-a-utility-function)

## What are Generics?

Generics in TypeScript allow you to create reusable components that work with any data type. They provide a way to create functions, classes, and interfaces that can operate on multiple types of data without sacrificing type safety. Generics are especially useful for creating components like data structures or utility functions that need to handle various types while maintaining strong typing.

## Generic Functions

A generic function is a function that can work with any type. The type is specified using a "type variable," which acts as a placeholder for the actual type that will be passed in when the function is used.

### Example

```typescript
function identity<T>(value: T): T {
  return value;
}

let numberIdentity = identity<number>(42);
let stringIdentity = identity<string>("Hello, TypeScript");
```

### Explanation

- **`<T>`**: The `T` in the function definition is a type variable that will be replaced by a specific type when the function is called.
- **`identity<number>(42)`**: Here, `T` is replaced with `number`.
- **`identity<string>("Hello, TypeScript")`**: Here, `T` is replaced with `string`.

## Generic Interfaces

Interfaces can also use generics to define types that work with a variety of data structures. This allows you to create flexible, reusable interfaces.

### Example

```typescript
interface Pair<T, U> {
  first: T;
  second: U;
}

let pair: Pair<number, string> = { first: 1, second: "one" };
```

### Explanation

- **`Pair<T, U>`**: This interface defines a generic pair with two types, `T` and `U`.
- **`Pair<number, string>`**: When creating a pair, `T` is replaced by `number` and `U` is replaced by `string`.

## Generic Classes

Classes can also be generic, allowing you to create flexible and reusable data structures.

### Example

```typescript
class Box<T> {
  content: T;

  constructor(content: T) {
    this.content = content;
  }

  getContent(): T {
    return this.content;
  }
}

let stringBox = new Box<string>("Hello, World");
console.log(stringBox.getContent()); // Output: "Hello, World"

let numberBox = new Box<number>(123);
console.log(numberBox.getContent()); // Output: 123
```

### Explanation

- **`Box<T>`**: The class `Box` is generic and can store content of any type `T`.
- **`new Box<string>("Hello, World")`**: Creates a `Box` that holds a string.
- **`new Box<number>(123)`**: Creates a `Box` that holds a number.

## Constraints in Generics

Sometimes, you might want to restrict the types that can be passed as generic parameters. You can do this by adding constraints to the type variables.

### Example

```typescript
interface Lengthwise {
  length: number;
}

function logLength<T extends Lengthwise>(item: T): void {
  console.log(item.length);
}

logLength("Hello"); // Works because strings have a length property
logLength([1, 2, 3]); // Works because arrays have a length property
logLength({ length: 10 }); // Works because the object has a length property
// logLength(123); // Error: number does not have a length property
```

### Explanation

- **`T extends Lengthwise`**: This ensures that `T` must be a type that has a `length` property.
- **`logLength("Hello")`**: Works because strings have a length property.
- **`logLength([1, 2, 3])`**: Works because arrays have a length property.

## Example: Using Generics in a Utility Function

Let's create a generic utility function that merges two objects into one.

### Example

```typescript
function merge<T, U>(obj1: T, obj2: U): T & U {
  return { ...obj1, ...obj2 };
}

const person = { name: "Alice" };
const details = { age: 30, city: "New York" };

const mergedObject = merge(person, details);
console.log(mergedObject); // Output: { name: "Alice", age: 30, city: "New York" }
```

### Explanation

- **`merge<T, U>`**: The `merge` function is generic, taking two objects of potentially different types.
- **`T & U`**: The return type is an intersection of `T` and `U`, meaning the result will have all the properties of both objects.
- **`{ ...obj1, ...obj2 }`**: The function uses the spread operator to merge the two objects.

This approach allows for a flexible yet type-safe way to combine objects.

## Sources 📖
- [TypeScript Documentation](https://www.typescriptlang.org/docs/)
- [TypeScript Handbook: Generics](https://www.typescriptlang.org/docs/handbook/generics.html)