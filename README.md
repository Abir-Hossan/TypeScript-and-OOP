# TypeScript & OOP Assignment

## Assignment Overview

This repository contains my solutions for the TypeScript and Object-Oriented Programming assignment. The coding section covers eight problems involving functions, optional parameters, union types, readonly tuples, rest parameters, interfaces, generics, type narrowing, classes, inheritance, access modifiers, and asynchronous Promises.

All eight fully described coding problems are implemented in one file, `solutions.ts`. The repository also includes two separate technical blog posts.

## Project Structure

```text
├── solutions.ts
├── type-aliases-vs-interfaces.md
├── type-narrowing.md
└── README.md
```

## Files

- **`solutions.ts`** – Contains the implementations for Problems 1–8.
- **`type-aliases-vs-interfaces.md`** – Discusses the differences between TypeScript type aliases and interfaces, with examples.
- **`type-narrowing.md`** – Explains type narrowing with `typeof`, `instanceof`, and the `in` operator.

## How to Run

Install TypeScript as a development dependency:

```bash
npm install --save-dev typescript
```

Compile the solutions using strict type checking:

```bash
npx tsc solutions.ts --target ES2020 --strict
```

## Blog Posts

1. [Type Aliases vs. Interfaces in TypeScript](./type-aliases-vs-interfaces.md)
2. [Type Narrowing in TypeScript](./type-narrowing.md)

## Assignment Note

The assignment's coding requirements also mention `getUniqueNumbers`, `Product`, and `updateProductPrice`. However, no problem statements, examples, or expected behaviour are provided for these names. I have not invented their requirements or added speculative implementations. The solutions file therefore covers the eight problems that are fully described in the assignment brief.
