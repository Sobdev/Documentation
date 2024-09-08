### Type Assertions

![TypeScript Logo](https://www.typescriptlang.org/assets/images/icons/favicon-32x32.png)

[TypeScript Documentation](https://www.typescriptlang.org/docs/)

## Index
1. [What are Type Assertions?](#what-are-type-assertions)
2. [Why Use Type Assertions?](#why-use-type-assertions)
3. [Type Assertion Syntax](#type-assertion-syntax)
4. [Type Assertions vs Type Casting](#type-assertions-vs-type-casting)
5. [Example: Using Type Assertions with DOM Elements](#example-using-type-assertions-with-dom-elements)

## What are Type Assertions?

Type assertions in TypeScript are a way of telling the TypeScript compiler that you know the type of a value better than it does. This allows you to override TypeScript's type inference in certain situations and force a variable to be treated as a specific type.

Type assertions don’t change the actual type of the variable during runtime—they only affect the type checking at compile-time.

## Why Use Type Assertions?

Type assertions are useful in scenarios where you have more information about the type of a value than TypeScript does, such as:

- When interacting with the DOM in web applications.
- When working with dynamic data from APIs.
- When migrating JavaScript code to TypeScript and type inference is insufficient.

For example, if you are working with an API that returns a broad type like `any`, you can assert that the value is a more specific type that you know how to handle.

## Type Assertion Syntax

There are two ways to write a type assertion in TypeScript:

### 1. Angle-Bracket Syntax

```typescript
let someValue: any = "Hello, TypeScript";
let strLength: number = (<string>someValue).length;
```

### 2. `as` Syntax

```typescript
let someValue: any = "Hello, TypeScript";
let strLength: number = (someValue as string).length;
```

Both syntaxes achieve the same result, but the `as` syntax is more commonly used and is preferred when working with JSX (React) since the angle-bracket syntax can conflict with JSX syntax.

## Type Assertions vs Type Casting

Type assertions in TypeScript are different from type casting in languages like C++ or Java. Type assertions do not perform any runtime conversion or checking—they simply instruct the TypeScript compiler to treat a value as a different type for the purposes of type checking.

In contrast, type casting in other languages can modify the data or transform it into another type at runtime.

## Example: Using Type Assertions with DOM Elements

Type assertions are often used when working with DOM elements in TypeScript. For example, when interacting with the DOM using `document.getElementById`, TypeScript returns a general type of `HTMLElement | null`. To safely manipulate an element, you often need to assert the specific type of the element (e.g., `HTMLInputElement`).

### Example

```typescript
const inputElement = document.getElementById("user-input") as HTMLInputElement;

inputElement.value = "Hello, world!";
```

### Explanation

- **`getElementById`**: By default, `getElementById` returns an `HTMLElement | null`. To interact with the `value` property, you need to assert that the element is an `HTMLInputElement` using the `as HTMLInputElement` syntax.
- **Type Safety**: This ensures that you have access to the correct properties and methods specific to the `HTMLInputElement` type, such as `value`.

### Handling `null` Cases

Since `getElementById` can return `null`, it's good practice to handle that case explicitly:

```typescript
const inputElement = document.getElementById("user-input");

if (inputElement) {
  (inputElement as HTMLInputElement).value = "Hello, world!";
}
```

Here, we first check if `inputElement` is not `null` before asserting the type.

## Example: Using Type Assertions with API Data

When fetching data from an API, the response type might be `any`, especially if the API schema isn’t strongly typed. You can use type assertions to ensure that TypeScript understands the structure of the data.

```typescript
interface User {
  id: number;
  name: string;
  email: string;
}

async function fetchUserData(): Promise<void> {
  const response = await fetch("https://api.example.com/user");
  const data = await response.json();

  const user = data as User; // Assert that the data is of type User
  console.log(user.name);
}
```

### Explanation

- **API Response**: The `fetch` API returns `any` by default when using `response.json()`. We use a type assertion to specify that the data should be treated as a `User` object.
- **Type Safety**: By asserting the type, we gain access to the properties of the `User` type (like `name` and `email`).

## Sources 📖
- [TypeScript Documentation](https://www.typescriptlang.org/docs)
- [Type Assertions](https://www.typescriptlang.org/docs/handbook/2/everyday-types.html#type-assertions)