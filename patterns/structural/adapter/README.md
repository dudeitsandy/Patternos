# Adapter

## Intent

Convert the interface of a class into another interface that clients expect. Adapter lets classes work together that couldn't otherwise because of incompatible interfaces.

## Also Known As

Wrapper

## Motivation

An off-the-shelf component may have a different interface than what is expected in an existing system. An Adapter wraps the component and translates calls so the existing system can use it without modification.

## Applicability

Use the Adapter pattern when:
- You want to use an existing class, but its interface does not match the one you need.
- You want to create a reusable class that cooperates with unrelated or unforeseen classes.
- You need to use several existing subclasses but it's impractical to adapt their interface by subclassing each one.

## Structure

```
Client --> Target (interface)
               ^
               |
            Adapter
               |
            Adaptee
```

## Participants

- **Target** — defines the domain-specific interface that the Client uses.
- **Client** — collaborates with objects conforming to the Target interface.
- **Adaptee** — defines an existing interface that needs adapting.
- **Adapter** — adapts the interface of Adaptee to the Target interface.

## Consequences

- A class adapter commits to a concrete Adaptee class.
- An object adapter lets a single Adapter work with many Adaptees.
- Makes it harder to override Adaptee behavior.

## Related Patterns

- Bridge has a structure similar to an object adapter but has a different intent.
- Decorator enhances another object without changing its interface.
- Proxy provides a surrogate for another object, and its interface is identical to the object it proxies.
