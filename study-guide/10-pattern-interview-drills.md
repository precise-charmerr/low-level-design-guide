# Pattern Interview Drills

Use these as rapid-fire questions after implementing a problem.

## Strategy

**Prompt:** Pricing differs for weekday, weekend, and premium customers.

Ask yourself:

- What is the varying behavior?
- What is the stable workflow?
- Can a new pricing algorithm be added without editing the workflow?

## Factory

**Prompt:** The system creates Card, UPI, and Wallet payment processors from a payment method.

Ask:

- Who should know the concrete classes?
- What belongs in the factory?
- Is a factory actually needed if construction is trivial?

## Observer

**Prompt:** When an order is shipped, several consumers need a notification.

Ask:

- Who owns subscription state?
- What happens when one observer fails?
- Is synchronous notification acceptable?

## State

**Prompt:** An order can be CREATED, PAID, SHIPPED, and DELIVERED.

Ask:

- Which transitions are valid?
- Where should invalid transitions be rejected?
- Does a large conditional become hard to maintain?

## Decorator

**Prompt:** Add logging, metrics, retry, or authorization around an existing service.

Ask:

- Can behavior be composed?
- Does the wrapper preserve the original contract?

## Chain of Responsibility

**Prompt:** A request passes through authentication, authorization, validation, rate limiting, and business logic.

Ask:

- Does order matter?
- Can a handler stop the chain?
- Should every handler know about every other handler?

## Interview rule

For every pattern you mention, give the interviewer three things:

1. **Problem:** what was difficult without the pattern?
2. **Structure:** what abstraction did you introduce?
3. **Trade-off:** what complexity did the pattern add?
