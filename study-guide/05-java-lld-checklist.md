# Java LLD Checklist

For Java interviews, be comfortable implementing LLDs with these language features.

## Core language

- Classes and objects
- Interfaces and abstract classes
- `extends` vs `implements`
- Method overriding and overloading
- `final`
- `static`
- Access modifiers
- Composition
- Enums
- Records where appropriate
- Generics
- Exceptions

## Collections

Know the behavior and typical use of:

- `ArrayList`
- `LinkedList`
- `HashMap`
- `HashSet`
- `TreeMap`
- `TreeSet`
- `Queue`
- `Deque`
- `PriorityQueue`
- `ConcurrentHashMap`

Know:

- equality and `hashCode`
- hashing
- ordering
- complexity
- mutation hazards when objects are map/set keys

## Modern Java

Be able to use sensibly:

- lambdas
- streams
- `Optional`
- method references
- functional interfaces
- `Comparator`

Don't use streams merely to make simple code shorter.

## Concurrency

Know the purpose and tradeoffs of:

- `synchronized`
- `Lock`
- `ReentrantLock`
- `volatile`
- atomic classes
- executors
- futures
- concurrent collections
- producer/consumer
- race conditions
- deadlocks

For an LLD interview, explain **where shared mutable state exists** before reaching for concurrency primitives.

## Exceptions

Distinguish:

- checked exceptions
- unchecked exceptions
- validation/business exceptions
- infrastructure failures

Avoid catching `Exception` everywhere.

## Testing

For a machine-coding solution, have a small set of tests for:

```text
happy path
boundary condition
invalid operation
duplicate operation
resource unavailable
state transition
```

## Clean Java habits

Prefer:

```java
private final Dependency dependency;

public Service(Dependency dependency) {
    this.dependency = dependency;
}
```

over hidden global state and field injection.

Keep domain objects meaningful rather than turning every operation into a static utility.
