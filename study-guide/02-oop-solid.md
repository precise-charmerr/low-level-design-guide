# OOP + SOLID Refresher

## OOP

### Encapsulation

Keep state and the operations that protect its invariants together.

Bad:

```java
account.balance -= amount;
```

Better:

```java
account.withdraw(amount);
```

The object can enforce rules such as insufficient balance.

### Abstraction

Expose what a client needs while hiding implementation details.

```java
interface PaymentProcessor {
    PaymentResult pay(Money amount);
}
```

The caller does not need to know how a card or wallet payment is implemented.

### Inheritance

Use when the subtype genuinely satisfies the base type's contract.

Do not use inheritance just to reuse a few methods.

### Polymorphism

Program to a common contract:

```java
PaymentProcessor processor = new CardPaymentProcessor();
processor.pay(amount);
```

The client can later use another implementation without changing its core flow.

## SOLID

### S — Single Responsibility

One class should have one coherent reason to change.

Bad:

```text
OrderService
  + calculatePrice
  + sendEmail
  + generatePDF
  + saveToDatabase
  + processPayment
```

Prefer focused collaborators.

### O — Open/Closed

New behavior should ideally be added by introducing a new implementation rather than repeatedly editing a large conditional.

### L — Liskov Substitution

A subtype must honor the expectations established by its abstraction.

If callers must constantly check the concrete subtype, the abstraction may be wrong.

### I — Interface Segregation

Prefer small role-oriented interfaces over giant interfaces.

### D — Dependency Inversion

High-level policy should depend on abstractions, not concrete implementation details.

```java
class OrderService {
    private final PaymentProcessor paymentProcessor;

    OrderService(PaymentProcessor paymentProcessor) {
        this.paymentProcessor = paymentProcessor;
    }
}
```

## A practical SOLID test

When adding a new requirement, ask:

```text
Will I add a new class?
Will I modify a giant if/else?
Will an unrelated class need to change?
Can I test this class without starting the entire application?
Can I replace one implementation with another?
```

These questions are often more useful in an interview than reciting definitions.
