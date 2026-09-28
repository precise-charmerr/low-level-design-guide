# LLD Interview Flow

Use this sequence during an object-oriented design or machine-coding interview.

## 1. Clarify requirements

Ask:

- What are the core use cases?
- Who are the actors?
- What operations are mandatory?
- What is explicitly out of scope?
- Are there limits or concurrency requirements?
- Do we need persistence, notifications, payments, search, or scheduling?
- Which behaviors are likely to change?

Do not start coding immediately.

## 2. Extract the nouns

Turn important domain concepts into candidate entities.

Example:

```text
Parking Lot
  -> Floor
  -> Parking Spot
  -> Vehicle
  -> Ticket
  -> Payment
```

Then remove concepts that do not need state or behavior.

## 3. Extract the verbs

Turn important operations into candidate responsibilities.

```text
park()
unpark()
findAvailableSpot()
calculateFee()
makePayment()
```

A class should own behavior that naturally belongs to its data.

## 4. Decide relationships

Know the difference between:

- Association
- Aggregation
- Composition
- Inheritance
- Dependency
- Interface implementation

Prefer composition when behavior can vary independently.

## 5. Define contracts

Use interfaces when:

- multiple implementations are plausible,
- behavior is expected to change,
- a strategy can be swapped,
- the client should depend on an abstraction.

Do not create interfaces mechanically for every class.

## 6. Pick patterns only when they solve a problem

Typical mappings:

| Problem | Useful pattern |
|---|---|
| Multiple interchangeable algorithms | Strategy |
| Object creation varies | Factory |
| Complex object construction | Builder |
| One state change notifies many consumers | Observer |
| Request passes through handlers | Chain of Responsibility |
| Object behavior changes with state | State |
| Add behavior without modifying core object | Decorator |
| Simplify a complex subsystem | Facade |
| Need one shared coordinator | Singleton — use carefully |

## 7. Walk through one end-to-end flow

For example:

```text
Client
  -> Manager
  -> Service
  -> Strategy / Repository
  -> Domain object state change
  -> Result
```

Explain which object calls which method and why.

## 8. Discuss extensibility

Good follow-ups:

- What if a new vehicle type is added?
- What if pricing changes?
- What if a new payment method is added?
- What if we support multiple floors?
- What if two users perform the operation concurrently?
- What if the requirement changes tomorrow?

Your design should absorb likely changes locally.

## 9. Handle failure paths

Mention:

- invalid input
- missing entity
- duplicate operation
- unavailable resource
- invalid state transition
- payment failure
- concurrent update
- partial operation

## 10. Only then optimize

For machine coding, prioritize:

1. Correct behavior
2. Clean object model
3. Separation of responsibilities
4. Extensibility
5. Testability
6. Performance improvements where justified

Don't introduce distributed-system complexity into a local LLD problem unless the interviewer asks for it.
