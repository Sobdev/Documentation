### Interfaces and Type Aliases

![TypeScript Logo](https://www.typescriptlang.org/assets/images/icons/favicon-32x32.png)

[TypeScript Documentation](https://www.typescriptlang.org/docs/)

## Index
1. [What are Interfaces?](#what-are-interfaces)
2. [Defining Interfaces](#defining-interfaces)
3. [Optional Properties and Readonly Properties](#optional-properties-and-readonly-properties)
4. [Extending Interfaces](#extending-interfaces)
5. [Type Aliases](#type-aliases)
6. [Interfaces vs Type Aliases](#interfaces-vs-type-aliases)
7. [Example: Using Interfaces and Type Aliases](#example-using-interfaces-and-type-aliases)

## What are Interfaces?

Interfaces in TypeScript are a way to define the shape of an object. They describe what properties an object should have and what types those properties should be. Interfaces help you ensure that different objects in your application adhere to a certain structure, improving type safety and code consistency.

## Defining Interfaces

To define an interface, you use the `interface` keyword followed by the name of the interface. Inside the interface, you list the properties and their types.

### Example

```typescript
interface User {
  id: number;
  name: string;
  email: string;
}

const user: User = {
  id: 1,
  name: "John Doe",
  email: "john.doe@example.com"
};
```

In this example, the `User` interface defines that a `User` object should have an `id` (a number), a `name` (a string), and an `email` (a string).

## Optional Properties and Readonly Properties

Interfaces in TypeScript can also define optional properties and readonly properties.

### Optional Properties

To make a property optional, you add a `?` after the property name.

```typescript
interface User {
  id: number;
  name: string;
  email?: string; // Optional property
}
```

In this example, the `email` property is optional. This means that a `User` object can either include the `email` property or omit it entirely.

### Readonly Properties

To make a property readonly, you add the `readonly` modifier before the property name. Readonly properties cannot be modified after the object is created.

```typescript
interface User {
  readonly id: number;
  name: string;
  email?: string;
}
```

In this example, the `id` property is readonly. Once a `User` object is created, the `id` cannot be changed.

## Extending Interfaces

TypeScript allows you to extend interfaces, meaning you can create a new interface based on an existing one, adding new properties or modifying existing ones.

### Example

```typescript
interface Person {
  name: string;
  age: number;
}

interface Employee extends Person {
  employeeId: number;
  department: string;
}

const employee: Employee = {
  name: "Alice",
  age: 30,
  employeeId: 1234,
  department: "Engineering"
};
```

In this example, the `Employee` interface extends the `Person` interface, inheriting its properties and adding `employeeId` and `department`.

## Type Aliases

Type aliases are another way to define types in TypeScript. They are similar to interfaces but are more flexible, as they can describe primitives, unions, tuples, and other types in addition to objects.

### Example

```typescript
type ID = number | string;

type User = {
  id: ID;
  name: string;
  email?: string;
};

const user: User = {
  id: "abc123",
  name: "Jane Doe",
  email: "jane.doe@example.com"
};
```

In this example, the `ID` type alias defines a type that can be either a `number` or a `string`. The `User` type alias is similar to an interface but is defined using the `type` keyword.

## Interfaces vs Type Aliases

While both interfaces and type aliases can be used to define the structure of objects, they have some differences:

- **Interfaces**: Can be extended using `extends` and can merge with other interfaces with the same name (declaration merging).
- **Type Aliases**: More flexible, can define unions, intersections, and other advanced types, but cannot be merged.

### When to Use Which?

- Use **interfaces** when you need to define the structure of an object and may need to extend or merge it.
- Use **type aliases** when you need to define unions, intersections, or more complex types that go beyond objects.

## Example: Using Interfaces and Type Aliases

Let's create a simple example that uses both interfaces and type aliases to define types in a TypeScript application.

```typescript
type ID = number | string;

interface Person {
  id: ID;
  name: string;
  age: number;
}

interface Employee extends Person {
  employeeId: number;
  department: string;
}

const employee: Employee = {
  id: "emp123",
  name: "Bob",
  age: 40,
  employeeId: 9876,
  department: "Sales"
};

function getEmployeeInfo(emp: Employee): string {
  return `Employee ${emp.name} works in the ${emp.department} department and is ${emp.age} years old.`;
}

console.log(getEmployeeInfo(employee));
```

### Explanation

- **Type Alias for ID**: The `ID` type alias allows `id` to be either a `number` or a `string`.
- **Person Interface**: Defines basic properties that all persons have.
- **Employee Interface**: Extends `Person` and adds more specific properties for an employee.
- **getEmployeeInfo Function**: Takes an `Employee` object and returns a string with information about the employee.

## Sources 📖
- [TypeScript Documentation](https://www.typescriptlang.org/docs/)
- [TypeScript Handbook](https://www.typescriptlang.org/docs/handbook/intro.html)
