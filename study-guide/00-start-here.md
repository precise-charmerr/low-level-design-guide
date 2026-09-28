# Start Here

This repository is intentionally organized for **learning LLD by building**, not by reading hundreds of pages in sequence.

## The loop

For every problem:

```text
Understand requirements
        ↓
Identify entities
        ↓
Assign responsibilities
        ↓
Choose relationships
        ↓
Find variability
        ↓
Introduce interfaces / patterns only where useful
        ↓
Draw the flow
        ↓
Implement
        ↓
Test edge cases
        ↓
Explain extensibility + trade-offs
```

## Your first problem: Parking Lot

Start with:

`source/awesome-low-level-design/problems/parking-lot.md`

Do **not** immediately copy the implementation.

First design these pieces yourself:

```text
ParkingLot
Floor
ParkingSpot
Vehicle
Ticket
Payment
PricingStrategy
```

Then answer:

1. Who finds a floor?
2. Who finds a spot?
3. Who changes spot state?
4. Who creates the ticket?
5. Where should `canFit(vehicle)` live?
6. How do we look up a parked vehicle/ticket without scanning every spot?
7. Where should pricing vary?
8. What happens if two vehicles try to take the same spot?
9. Is a Singleton actually necessary?
10. What changes if motorcycles can use larger spots?

These questions force the important LLD skills: ownership, cohesion, polymorphism, state transitions, data structures, and concurrency.

## Recommended practice sequence

### Phase 1 — Foundations

1. OOP
2. SOLID
3. Composition vs inheritance
4. Association / aggregation / composition
5. Interfaces and abstract classes
6. UML class + sequence diagrams

### Phase 2 — Patterns through code

1. Strategy
2. Factory
3. Builder
4. Observer
5. State
6. Decorator
7. Adapter
8. Facade
9. Chain of Responsibility
10. Command

Use the Java examples in `source/awesome-low-level-design/design-patterns/java/` while learning each pattern.

### Phase 3 — Small LLDs

1. Tic-Tac-Toe
2. Vending Machine
3. Snake & Ladder
4. LRU Cache
5. Elevator
6. Parking Lot

### Phase 4 — Medium machine coding

1. Splitwise
2. Ride Sharing
3. FoodKart / food ordering
4. Event Calendar
5. Hotel Management
6. Library Management
7. Movie Ticket Booking
8. Stock Exchange
9. Property Hunt
10. Ledger

### Phase 5 — Larger exercises

Use the larger implementations in both source repositories and practice explaining how you would evolve them for production.

## Rule for every interview problem

Don't begin with:

> "Which design pattern should I use?"

Begin with:

> "What can change independently?"

The answer usually tells you where an abstraction belongs.
