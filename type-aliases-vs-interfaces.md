# Type Aliases vs. Interfaces in TypeScript: What Is the Difference?

## Introduction

When working with TypeScript, we often need to describe what an object should look like. Two common ways to do this are interfaces and type aliases. They can look almost identical when we use them for objects, but they are not exactly the same. Knowing how they differ makes it easier to choose the right one for a particular situation.

## Detailed Explanation

An interface is mainly used to describe the structure an object should follow. It can also be extended by another interface, which is useful when two related objects share some properties.

```typescript
interface User {
  name: string;
  age: number;
}

interface Admin extends User {
  permissions: string[];
}
```

In this example, `Admin` gets the `name` and `age` properties from `User` and adds `permissions`. Interfaces also support declaration merging. If an interface with the same name is declared again in the same scope, TypeScript combines the declarations.

A type alias gives a name to a type. It can describe an object, but it can also represent unions, intersections, tuples, primitive types, and function signatures.

```typescript
type Status = "active" | "inactive";

type IdentifiedUser = User & {
  id: number;
};
```

Here, `Status` allows only two string values, while `IdentifiedUser` combines the properties of `User` with an `id`. Unlike interfaces, type aliases cannot be reopened through declaration merging.

## Conclusion

I would usually choose an interface for an object structure that may need to be extended or merged. A type alias is more suitable when I need unions, tuples, or combinations of different types. Both can describe objects, so consistency across a project also matters.
