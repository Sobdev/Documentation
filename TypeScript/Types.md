### Types

![TypeScript Logo](https://www.typescriptlang.org/assets/images/icons/favicon-32x32.png)

[TypeScript Documentation](https://www.typescriptlang.org/docs/)

## Index
1. [What is TypeScript?](#what-is-typescript)
2. [Setting Up a TypeScript Project](#setting-up-a-typescript-project)
3. [Basic Types](#basic-types)
4. [Type Annotations](#type-annotations)
5. [Example: Using Basic Types](#example-using-basic-types)

## What is TypeScript?

TypeScript is a strongly typed programming language that builds on JavaScript, giving you better tooling at any scale. It is a superset of JavaScript, meaning that any valid JavaScript code is also valid TypeScript code. TypeScript adds optional static types, classes, and interfaces, which helps developers catch errors early during development, rather than at runtime.

## Setting Up a TypeScript Project

To start using TypeScript, you need to install it in your project and set up a configuration file. Here’s how you can do that:

### Steps to Install and Set Up

1. **Initialize a New Project (if you haven't already)**:
   ```bash
   mkdir my-typescript-project
   cd my-typescript-project
   npm init -y
   ```

2. **Install TypeScript via npm**:
   ```bash
   npm install typescript --save-dev
   ```

3. **Create a `tsconfig.json` File**:
   The `tsconfig.json` file specifies the root files and the compiler options required to compile the project.

   Generate it using the TypeScript command:
   ```bash
   npx tsc --init
   ```

   A basic `tsconfig.json` might look like this:

   ```json
   {
     "compilerOptions": {
       "target": "es6",
       "module": "commonjs",
       "strict": true,
       "esModuleInterop": true,
       "skipLibCheck": true,
       "forceConsistentCasingInFileNames": true
     }
   }
   ```

4. **Create a TypeScript File**:
   Create a `.ts` file where you can start writing TypeScript code, for example, `index.ts`.

5. **Compile TypeScript to JavaScript**:
   To compile your TypeScript files into JavaScript, run:
   ```bash
   npx tsc
   ```
   This command will generate the corresponding `.js` files from your `.ts` files.

## Basic Types

TypeScript provides several built-in data types that you can use to ensure your code is type-safe. Here are some of the most commonly used types:

- **`number`**: Represents numeric values.
- **`string`**: Represents text data.
- **`boolean`**: Represents `true` or `false`.
- **`array`**: Represents a collection of values, with a specific type for each element.
- **`tuple`**: Represents an array with a fixed number of elements, where each element can have a different type.
- **`enum`**: Represents a set of named constants.
- **`any`**: A dynamic type that can hold any value (use sparingly).
- **`void`**: Represents the absence of a value, often used in functions that do not return anything.
- **`null` and `undefined`**: Represent null and undefined values.

### Examples of Basic Types

```typescript
let count: number = 10;
let userName: string = "John Doe";
let isLoggedIn: boolean = true;

let numbers: number[] = [1, 2, 3];
let user: [string, number] = ["Alice", 25]; // Tuple

enum Direction {
  Up = 1,
  Down,
  Left,
  Right
}

let myDirection: Direction = Direction.Up;
```

## Type Annotations

Type annotations allow you to explicitly specify the type of a variable, function parameter, or return type. This helps in catching type-related errors early.

### Variable Annotations

You can declare variables with type annotations like this:

```typescript
let age: number = 30;
let firstName: string = "Jane";
```

### Function Annotations

Function parameters and return types can also have annotations:

```typescript
function add(a: number, b: number): number {
  return a + b;
}
```

In this example, the `add` function accepts two parameters of type `number` and returns a value of type `number`.

## Example: Using Basic Types

Let's put everything together with a simple example that demonstrates how TypeScript's types can be used in a basic application.

```typescript
enum Role {
  Admin,
  User,
  Guest
}

function greet(name: string, role: Role): string {
  return `Hello, ${name}! Your role is ${Role[role]}.`;
}

let message: string = greet("Alice", Role.User);
console.log(message);
```

### Explanation

- **Role Enum**: Defines different user roles (`Admin`, `User`, `Guest`).
- **greet Function**: Takes a `name` and `role` as arguments and returns a greeting message.
- **Type Safety**: The TypeScript compiler ensures that only valid types are passed to the `greet` function.

## Sources 📖
- [TypeScript Documentation](https://www.typescriptlang.org/docs/)
- [TypeScript Handbook](https://www.typescriptlang.org/docs/handbook/intro.html)
