# Type Narrowing in TypeScript: typeof, instanceof, and the in Operator

## Introduction

A TypeScript variable can sometimes hold more than one kind of value. This happens when we use a union type, such as `string | number`. Before using that value, we need to know which type it currently has. Type narrowing helps us do this. It uses checks in our code so TypeScript can treat a value as a more specific type inside a particular branch.

## Detailed Explanation

The `typeof` operator is useful for checking primitive types such as strings and numbers.

```typescript
function formatValue(value: string | number): string {
  if (typeof value === "string") {
    return value.trim().toLowerCase();
  }

  return value.toFixed(2);
}
```

If the value is a string, the function uses string methods. Otherwise, TypeScript knows it is a number and allows `toFixed()`.

The `instanceof` operator is useful when a union contains class instances. It checks whether an object was created from a particular class or has that class in its prototype chain.

```typescript
class Dog {
  bark(): string {
    return "Woof!";
  }
}

function describe(value: Dog | Date): string {
  if (value instanceof Dog) {
    return value.bark();
  }

  return value.toDateString();
}
```

The `in` operator checks whether a property exists on an object. It helps distinguish object types that have different properties.

```typescript
type Admin = { name: string; permissions: string[] };
type Customer = { name: string; orderCount: number };

function getAccessInfo(person: Admin | Customer): string {
  if ("permissions" in person) {
    return person.permissions.join(", ");
  }

  return `Orders: ${person.orderCount}`;
}
```

The presence of `permissions` tells TypeScript which object shape is being handled.

## Conclusion

Use `typeof` for primitive values, `instanceof` for class instances, and `in` to check object properties. These checks make union-type code easier to follow and help prevent unsafe assumptions.
