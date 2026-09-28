# LLD Practice Template

Copy this file for every problem you practice.

## 1. Problem

Write the problem in 3–5 sentences.

## 2. Functional requirements

- 
- 
- 

## 3. Assumptions

- 
- 
- 

## 4. Core entities

| Entity | Important state | Main responsibility |
|---|---|---|
| | | |
| | | |
| | | |

## 5. Relationships

```text
Write the important associations/compositions/inheritance here.
```

## 6. Interfaces

List only abstractions that provide real variability.

```text
Interface:
Why it exists:
Implementations:
```

## 7. Design patterns

| Pattern | Where | Why |
|---|---|---|
| | | |

## 8. Main flow

```text
Client
  -> 
  ->
  ->
```

## 9. Edge cases

- 
- 
- 

## 10. Concurrency

Is shared mutable state present?

If yes:

```text
Shared state:
Race:
Protection:
```

## 11. Extensibility

If the interviewer adds:

> "Now support ______."

Which classes change?

Which classes should remain unchanged?

## 12. Complexity

Document the important operations:

```text
Operation:
Time:
Space:
Reason:
```

## 13. Tests

- [ ] happy path
- [ ] invalid input
- [ ] boundary
- [ ] duplicate operation
- [ ] unavailable resource
- [ ] state transition

## 14. Interview explanation

Explain the design in this order:

```text
requirements
  -> entities
  -> relationships
  -> interfaces
  -> patterns
  -> main flow
  -> edge cases
  -> extensibility
  -> tradeoffs
```
