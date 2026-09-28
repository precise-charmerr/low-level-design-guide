# Common LLD Follow-ups

After your initial design, expect questions like these.

## "What if we add another type?"

Example:

> Add a new payment method.

Good answer:

- identify the abstraction that already represents payment behavior
- add an implementation
- avoid changing unrelated business logic

## "What if the algorithm changes?"

Think Strategy.

## "What if there are millions of objects?"

Separate object-model concerns from persistence/indexing concerns. Explain the data structure you use for lookups.

## "What if two requests happen simultaneously?"

Identify shared mutable state and define the consistency boundary.

## "What if one operation fails halfway?"

Discuss validation order, transaction boundaries, rollback/compensation, and idempotency where relevant.

## "Why this class owns this method?"

Answer in terms of:

- information ownership
- invariant protection
- cohesion
- change responsibility

## "Why interface instead of abstract class?"

Use an interface when you primarily need a contract/capability and multiple unrelated implementations can satisfy it.

Use an abstract class when shared state/behavior and a meaningful base-type relationship justify inheritance.

## "Why not use a Singleton?"

Explain whether global uniqueness is actually a requirement. If dependency injection can manage lifecycle and sharing, that is often easier to test.

## "Why did you choose this collection?"

State:

```text
access pattern
ordering requirement
uniqueness requirement
expected size
mutation pattern
concurrency requirement
```

Then select the collection.

## "What would you change for production?"

Separate the answer into:

```text
LLD object model
persistence
transactions
concurrency
caching
observability
security
scaling
failure handling
```

This keeps a machine-coding answer from becoming an unfocused system-design answer.
