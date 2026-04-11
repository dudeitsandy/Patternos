# Observer

## Intent

Define a one-to-many dependency between objects so that when one object changes state, all its dependents are notified and updated automatically.

## Also Known As

Dependents, Publish-Subscribe

## Motivation

A common side effect of partitioning a system into cooperating objects is the need to maintain consistency. You don't want to achieve consistency by making classes tightly coupled, because that reduces their reusability. The Observer pattern describes how to establish these dependencies.

## Applicability

Use the Observer pattern when:
- An abstraction has two aspects, one dependent on the other.
- A change to one object requires changing others, and you don't know how many objects need to change.
- An object should be able to notify other objects without making assumptions about who these objects are.

## Structure

```
Subject                     Observer (interface)
  - observers: []     <---- + update()
  + attach(Observer)              ^
  + detach(Observer)              |
  + notify()              ConcreteObserver
       |                    - subject: Subject
       v                    + update()
ConcreteSubject
  - state
  + getState()
  + setState()
```

## Participants

- **Subject** — knows its observers and provides interfaces for attaching and detaching Observer objects.
- **Observer** — defines an updating interface for objects that should be notified of changes in a subject.
- **ConcreteSubject** — stores state of interest to ConcreteObserver objects.
- **ConcreteObserver** — maintains a reference to a ConcreteSubject and implements the Observer updating interface.

## Consequences

- Abstract coupling between Subject and Observer.
- Support for broadcast communication.
- Unexpected updates — observers don't know about each other.

## Related Patterns

- Mediator encapsulates the way objects interact with each other.
- Singleton can be used to make a subject or event bus accessible globally.
