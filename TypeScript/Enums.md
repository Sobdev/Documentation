### Working with Enums

![TypeScript Logo](https://www.typescriptlang.org/assets/images/icons/favicon-32x32.png)

[TypeScript Documentation](https://www.typescriptlang.org/docs/)

## Index
1. [What are Enums?](#what-are-enums)
2. [Numeric Enums](#numeric-enums)
3. [String Enums](#string-enums)
4. [Heterogeneous Enums](#heterogeneous-enums)
5. [Enum Members and Type Safety](#enum-members-and-type-safety)
6. [Example: Using Enums in a Switch Statement](#example-using-enums-in-a-switch-statement)

## What are Enums?

Enums (short for "enumerations") are a feature in TypeScript that allows you to define a set of named constants. These constants can be either numeric or string values. Enums are useful when you have a fixed set of related values that you want to represent in a type-safe way.

Enums make your code more readable and maintainable by replacing hard-coded values with descriptive names.

## Numeric Enums

The most common type of enum in TypeScript is the numeric enum. In a numeric enum, each member is assigned an auto-incremented numeric value starting from 0, unless explicitly specified otherwise.

### Example

```typescript
enum Direction {
  Up,
  Down,
  Left,
  Right
}

let move: Direction = Direction.Up;

console.log(move); // Output: 0
```

### Explanation

- **Auto-increment**: The `Direction` enum starts at `0` for `Up`, `1` for `Down`, `2` for `Left`, and `3` for `Right`.
- **Assignment**: You can assign an enum member to a variable like `move`, which will hold the numeric value associated with `Direction.Up`.

You can also start the numbering from a different value:

```typescript
enum Direction {
  Up = 1,
  Down,
  Left,
  Right
}

console.log(Direction.Up); // Output: 1
console.log(Direction.Down); // Output: 2
```

## String Enums

In a string enum, each member is assigned a string value. This is useful when the enum values need to be more descriptive or when you want the values to remain consistent and not change due to auto-increment.

### Example

```typescript
enum Status {
  Success = "SUCCESS",
  Failure = "FAILURE",
  Pending = "PENDING"
}

let currentStatus: Status = Status.Success;

console.log(currentStatus); // Output: "SUCCESS"
```

### Explanation

- **Explicit Strings**: Each member of the `Status` enum is explicitly assigned a string value, making it clear and unambiguous.

## Heterogeneous Enums

TypeScript also allows you to create enums that have both numeric and string values. These are called heterogeneous enums. However, it's generally recommended to avoid them unless there's a specific need, as they can make the code harder to understand.

### Example

```typescript
enum Mixed {
  No = 0,
  Yes = "YES"
}

console.log(Mixed.No);  // Output: 0
console.log(Mixed.Yes); // Output: "YES"
```

### Explanation

- **Mixed Values**: `Mixed.No` is assigned a numeric value, while `Mixed.Yes` is assigned a string value.

## Enum Members and Type Safety

Enums in TypeScript provide type safety by ensuring that variables assigned to enum types can only have the values defined in the enum. This prevents accidental assignment of invalid values.

### Example

```typescript
enum Colors {
  Red,
  Green,
  Blue
}

let myColor: Colors = Colors.Green;

// TypeScript will throw an error if you try to assign a value not in the enum
// myColor = 4; // Error: Type '4' is not assignable to type 'Colors'.
```

### Explanation

- **Type Safety**: The `myColor` variable can only be assigned one of the values from the `Colors` enum. Assigning a value outside this range will cause a compile-time error.

## Example: Using Enums in a Switch Statement

Enums are particularly useful in switch statements, where they can replace hard-coded values with more meaningful names.

### Example

```typescript
enum Status {
  Success = "SUCCESS",
  Failure = "FAILURE",
  Pending = "PENDING"
}

function getStatusMessage(status: Status): string {
  switch (status) {
    case Status.Success:
      return "Operation was successful!";
    case Status.Failure:
      return "Operation failed.";
    case Status.Pending:
      return "Operation is pending.";
    default:
      return "Unknown status.";
  }
}

let message = getStatusMessage(Status.Pending);
console.log(message); // Output: "Operation is pending."
```

### Explanation

- **Switch Statement**: The `getStatusMessage` function uses a switch statement to return different messages based on the value of the `status` parameter.
- **Enum as Parameter**: The function's `status` parameter is typed as `Status`, ensuring that only valid enum values can be passed.

This approach makes the code more readable and reduces the risk of errors from using incorrect status values.

## Sources 📖
- [TypeScript Documentation](https://www.typescriptlang.org/docs/)
- [Enums in TypeScript](https://www.typescriptlang.org/docs/handbook/enums.html)