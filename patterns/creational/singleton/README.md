# Singleton

## Intent

Ensure a class has only one instance and provide a global access point to it.

## Also Known As

Single-instance

## Motivation

Sometimes it is important to have exactly one instance of a class — for example,
a single configuration manager or connection pool shared across an application.

## Applicability

Use the Singleton pattern when:
- There must be exactly one instance of a class, and it must be accessible from a well-known access point.
- The sole instance should be extensible by subclassing, and clients should be able to use an extended instance without modifying their code.

## Structure

```
Singleton
  - instance: Singleton  (private static)
  + getInstance(): Singleton
  - Singleton()           (private constructor)
```

## Participants

- **Singleton** — defines an `getInstance` operation that lets clients access its unique instance.

## Consequences

- Controlled access to the sole instance.
- Reduced namespace pollution compared to global variables.
- Permits refinement of operations and representation through subclassing.
- More flexible than class operations.

## Related Patterns

- Abstract Factory, Builder, and Prototype can all be implemented as Singletons.
