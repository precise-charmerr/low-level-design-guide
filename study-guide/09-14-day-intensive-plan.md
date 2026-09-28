# 14-Day LLD Intensive Plan

Designed for an engineer preparing for Java-oriented LLD / machine-coding interviews.

## Days 1–2 — Object modeling

- OOP pillars
- interfaces vs abstract classes
- composition vs inheritance
- association / aggregation / composition
- immutability
- enums and value objects

Practice: Tic-Tac-Toe.

## Days 3–4 — SOLID + clean design

- SRP
- OCP
- LSP
- ISP
- DIP
- cohesion and coupling
- dependency injection

Practice: refactor a deliberately bad design.

## Days 5–7 — Patterns by implementation

Day 5: Strategy + Factory + Builder  
Day 6: Observer + State + Command  
Day 7: Adapter + Decorator + Facade + Chain of Responsibility

For each pattern:

```text
naive version
→ identify change
→ introduce abstraction
→ implement two variants
→ explain why the client stays unchanged
```

## Days 8–10 — Core LLDs

Day 8: Parking Lot + Vending Machine  
Day 9: Elevator + LRU Cache  
Day 10: Snake & Ladder + Movie Booking

For each problem, implement the core flow before adding optional features.

## Days 11–12 — Machine coding

Day 11: Splitwise + Ride Sharing  
Day 12: FoodKart + Event Calendar

Time-box each problem. At the end, explain your design aloud as if an interviewer were asking follow-ups.

## Day 13 — Advanced follow-ups

Practice:

- concurrency
- thread safety
- state transitions
- idempotency
- extensibility
- failure handling
- collection choice
- complexity

Pick two previous problems and redesign them under new requirements.

## Day 14 — Mock interview day

Do three rounds:

### Round 1 — 30 minutes

Small problem, no reference solution.

### Round 2 — 60–90 minutes

Machine-coding problem with tests.

### Round 3 — Review

For each design, answer:

- What would change most often?
- Which class has too many responsibilities?
- Which abstraction is premature?
- Where is shared mutable state?
- What would break if a new type is introduced?
- What would you change for production?
