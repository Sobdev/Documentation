### Union and Intersection Types

![TypeScript Logo](https://www.typescriptlang.org/assets/images/icons/favicon-32x32.png)

[TypeScript Documentation](https://www.typescriptlang.org/docs/)

## Index
1. [What are Union Types?](#what-are-union-types)
2. [What are Intersection Types?](#what-are-intersection-types)
3. [Type Narrowing with Union Types](#type-narrowing-with-union-types)
4. [Practical Uses of Intersection Types](#practical-uses-of-intersection-types)
5. [Example: Combining Union and Intersection Types](#example-combining-union-and-intersection-types)

## What are Union Types?

Union types in TypeScript allow you to define a variable or function parameter that can take more than one type. This is useful when you have a value that could be one of several types.

### Example

```typescript
let id: number | string;

id = 123; // valid
id = "ABC123"; // valid
// id = true; // Error: boolean is not assignable to type 'number | string'
```

### Explanation

- **`number | string`**: This is a union type that allows `id` to be either a `number` or a `string`. It provides flexibility when a variable can take multiple types while still maintaining type safety.

## What are Intersection Types?

Intersection types allow you to combine multiple types into one. A value of an intersection type must satisfy all the types that are part of the intersection. This is often useful when you want to merge the properties of multiple types into a single type.

### Example

```typescript
interface Person {
  name: string;
  age: number;
}

interface Employee {
  employeeId: number;
  position: string;
}

type EmployeePerson = Person & Employee;

const employee: EmployeePerson = {
  name: "Alice",
  age: 30,
  employeeId: 1234,
  position: "Manager"
};
```

### Explanation

- **`Person & Employee`**: The `EmployeePerson` type combines the properties of both `Person` and `Employee`. Any object of this type must have all the properties from both interfaces.

## Type Narrowing with Union Types

When working with union types, TypeScript allows you to "narrow" the type to a more specific one based on the context. This is typically done using type guards like `typeof`, `instanceof`, or custom checks.

### Example

```typescript
function printId(id: number | string): void {
  if (typeof id === "string") {
    console.log("ID as a string:", id.toUpperCase());
  } else {
    console.log("ID as a number:", id.toFixed(2));
  }
}
```

### Explanation

- **Type Guard (`typeof`)**: The `typeof` check is used to determine whether `id` is a string or a number, and TypeScript narrows the type based on that.

## Practical Uses of Intersection Types

Intersection types are especially useful when you want to combine multiple interfaces, such as when working with a model that includes properties from multiple sources. They allow for more type-safe code when merging data or working with complex models.

### Example: Combining Models

```typescript
interface