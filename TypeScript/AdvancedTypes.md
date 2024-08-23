### Advanced Types - Union and Intersection Types

![TypeScript Logo](https://www.typescriptlang.org/assets/images/icons/favicon-32x32.png)

[TypeScript Documentation](https://www.typescriptlang.org/docs/)

## Index
1. [Union Types](#union-types)
2. [Intersection Types](#intersection-types)
3. [Type Narrowing with Union Types](#type-narrowing-with-union-types)
4. [Practical Examples of Union and Intersection Types](#practical-examples-of-union-and-intersection-types)
5. [Example: Combining Union and Intersection Types](#example-combining-union-and-intersection-types)

## Union Types

Union types in TypeScript allow a variable to hold one of several types. This is useful when a value can be more than one type, but not at the same time. Union types are created using the `|` symbol between types.

### Example

```typescript
let id: number | string;

id = 101; // valid
id = "abc123"; // valid
id = true; // invalid, TypeScript will throw an error
```

In this example, `id` can be either a `number` or a `string`, but not a `boolean` or any other type.

## Intersection Types

Intersection types are the opposite of union types. They allow you to combine multiple types into one. An intersection type is created using the `&` symbol between types. The resulting type has all the properties of the combined types.

### Example

```typescript
interface Person {
  name: string;
  age: number;
}

interface Employee {
  employeeId: number;
}

type EmployeePerson = Person & Employee;

const employee: EmployeePerson = {
  name: "John Doe",
  age: 30,
  employeeId: 1234
};
```

In this example, `EmployeePerson` is an intersection of `Person` and `Employee`. Any variable of type `EmployeePerson` must have all the properties from both `Person` and `Employee`.

## Type Narrowing with Union Types

When working with union types, TypeScript allows you to narrow down the type within a block of code. This is often done using type guards such as `typeof` or `instanceof`.

### Example

```typescript
function printId(id: number | string) {
  if (typeof id === "string") {
    console.log(`The ID is a string: ${id.toUpperCase()}`);
  } else {
    console.log(`The ID is a number: ${id}`);
  }
}
```

In this function, TypeScript narrows the type of `id` based on the result of the `typeof` check. If `id` is a string, TypeScript knows it can safely call string methods like `toUpperCase`. If `id` is a number, it handles it differently.

## Practical Examples of Union and Intersection Types

### Union Types in Function Parameters

Union types are useful in function parameters when the function can accept multiple types of input.

```typescript
function logValue(value: string | number) {
  console.log(`Logging value: ${value}`);
}

logValue(100); // valid
logValue("Hello, TypeScript!"); // valid
```

### Intersection Types for Combining Models

Intersection types are handy when you need to combine models in complex applications.

```typescript
interface Address {
  street: string;
  city: string;
  zipCode: string;
}

interface Contact {
  email: string;
  phone: string;
}

type UserProfile = Address & Contact;

const user: UserProfile = {
  street: "123 Main St",
  city: "Anytown",
  zipCode: "12345",
  email: "user@example.com",
  phone: "555-1234"
};
```

In this example, `UserProfile` combines properties from both `Address` and `Contact`, making it a more complex type that represents a user's complete profile.

## Example: Combining Union and Intersection Types

Let's create a more complex example that uses both union and intersection types to represent a scenario in a TypeScript application.

```typescript
interface Developer {
  name: string;
  skills: string[];
}

interface Manager {
  name: string;
  teamSize: number;
}

type Employee = Developer | Manager;

function describeEmployee(emp: Employee) {
  console.log(`Name: ${emp.name}`);
  
  if ("skills" in emp) {
    console.log(`Skills: ${emp.skills.join(", ")}`);
  }
  
  if ("teamSize" in emp) {
    console.log(`Manages a team of ${emp.teamSize} people.`);
  }
}

const dev: Developer = { name: "Alice", skills: ["JavaScript", "TypeScript"] };
const mgr: Manager = { name: "Bob", teamSize: 5 };

describeEmployee(dev); // Outputs Alice's skills
describeEmployee(mgr); // Outputs Bob's team size
```

### Explanation

- **Union Type (`Employee`)**: The `Employee` type can be either a `Developer` or a `Manager`.
- **Type Guard (`in`)**: We use the `in` operator to check if a certain property exists on the `emp` object to determine its specific type at runtime.
- **Flexible Function**: The `describeEmployee` function can handle both `Developer` and `Manager` objects appropriately.

## Sources 📖
- [TypeScript Documentation](https://www.typescriptlang.org/docs/)
- [TypeScript Handbook: Unions and Intersections](https://www.typescriptlang.org/docs/handbook/unions-and-intersections.html)