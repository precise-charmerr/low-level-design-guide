# Design Pattern Map

Use this as a recognition guide rather than a memorization list.

## Creational

### Factory

Use when object creation depends on a type/configuration and callers should not know the construction details.

```text
Client -> Factory -> Concrete Product
```

### Abstract Factory

Use when creating families of related objects.

### Builder

Use when an object has many optional parameters or construction steps.

### Prototype

Use when cloning an existing object is preferable to rebuilding it.

### Singleton

Use only when exactly one shared instance is a genuine domain/application requirement. Prefer dependency injection when possible.

## Structural

### Adapter

Make an incompatible API fit the interface expected by your code.

### Decorator

Wrap an object to add behavior dynamically.

### Facade

Provide a simpler API over a complicated subsystem.

### Composite

Treat individual objects and groups uniformly.

### Proxy

Control or augment access to another object.

### Bridge

Separate an abstraction from an implementation so both can evolve independently.

## Behavioral

### Strategy

Encapsulate interchangeable algorithms.

Classic LLD examples:

```text
PricingStrategy
PaymentStrategy
ParkingSpotSelectionStrategy
MatchingStrategy
```

### Observer

One-to-many notification.

```text
Subject -> subscribers
```

### State

Behavior changes according to internal state.

```text
Order: CREATED -> PAID -> SHIPPED -> DELIVERED
```

### Chain of Responsibility

A request can be handled by one of several handlers in sequence.

### Command

Represent an action as an object. Useful for queues, undo, auditing, and scheduling.

### Template Method

Keep an algorithm skeleton fixed while subclasses customize steps.

### Iterator

Traverse a collection without exposing its internal representation.

## Pattern-selection rule

Do not say:

> "I used Strategy because Strategy is a good pattern."

Say:

> "Pricing can vary independently from parking/booking logic, so I isolated the pricing algorithm behind an interface. That lets us add weekday, weekend, or dynamic pricing without changing the core flow."

That connects the pattern to a concrete change in requirements.
