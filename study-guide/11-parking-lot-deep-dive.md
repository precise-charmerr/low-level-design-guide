# Parking Lot Deep Dive

Parking Lot is an excellent first serious LLD because it combines object modeling, polymorphism, state, lookup structures, pricing, and concurrency.

## Baseline model

```text
ParkingLot
  └── Floor*
        └── ParkingSpot*

Vehicle
  ├── Car
  ├── Motorcycle
  └── Truck

Ticket
Payment
PricingStrategy
```

## Responsibility questions

### ParkingLot

Possible responsibility:

- coordinate the parking/unparking operation across floors

Avoid making it responsible for every detail.

### Floor

Natural responsibility:

- manage spots belonging to that floor
- find an appropriate available spot
- coordinate the spot's state change

### ParkingSpot

Natural responsibility:

- know its type/capacity
- know whether it is occupied
- enforce whether a vehicle can fit
- transition between available and occupied

A useful design question is whether `canFit(vehicle)` belongs on the spot or in a separate matching strategy. Both can be defensible; explain the change you are optimizing for.

### Ticket

Represents the parking session.

It should not become the owner of unrelated parking-lot state.

### PricingStrategy

Encapsulates fee calculation when pricing rules vary.

Examples:

```text
HourlyPricing
WeekendPricing
VehicleBasedPricing
DynamicPricing
```

## Lookup structure

If exit requires finding a ticket quickly, don't scan every spot by default.

Possible indexes:

```text
vehicleNumber -> ticket
spotId -> ticket
```

Choose the index based on the lookup operations the requirements actually need.

## Concurrency

Potential race:

```text
Thread A -> sees spot available
Thread B -> sees same spot available
Thread A -> occupies it
Thread B -> occupies it
```

The check-and-occupy operation must be atomic from the application's point of view.

## Singleton discussion

The supplied Parking Lot example uses Singleton. Treat that as something to discuss, not something to blindly copy.

Ask:

> Does the domain really require one globally accessible instance, or can the application own a `ParkingLot` instance and inject it where required?

Dependency injection is usually easier to test because it avoids hidden global state.

## Interview extension questions

Practice adding:

- multiple entry/exit gates
- motorcycles using larger spots
- electric-vehicle charging spots
- handicapped spots
- reservations
- different pricing rules
- lost ticket handling
- real-time availability display
- multiple concurrent gates
