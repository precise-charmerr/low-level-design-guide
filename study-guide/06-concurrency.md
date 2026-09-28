# Concurrency for LLD

Concurrency becomes relevant when multiple clients can mutate the same logical state.

## First identify the shared state

Examples:

```text
available parking spots
inventory quantity
account balance
seat availability
ride assignment
wallet balance
order status
```

Then ask:

> What happens if two threads execute this operation at the same time?

## Common race

```text
Thread A: read inventory = 1
Thread B: read inventory = 1
Thread A: buy
Thread B: buy
```

Both may succeed even though only one item existed.

## Interview-level solutions

Depending on the problem:

- synchronized critical section
- explicit lock
- atomic operation
- database transaction
- optimistic locking
- queue/serialized processing
- immutable state + replacement

Choose based on where the source of truth lives.

## Deadlock checklist

If multiple locks exist:

- acquire locks in a consistent order
- keep critical sections small
- avoid calling unknown code while holding a lock
- consider timeout-based locking where appropriate

## Important distinction

LLD interview code and production distributed systems are not the same thing.

If the interviewer asks for an in-memory machine-coding implementation, an appropriate in-memory synchronization strategy may be enough. If they ask for a multi-instance production architecture, discuss the database/cache/message-broker coordination separately.
