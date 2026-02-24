# Architectural Decisions

## Why JWT-Based Authentication?

JWT was chosen to support stateless authentication,
simplifying horizontal scalability and frontend integration.

## Why Separate Frontend and Backend Repositories?

- Clear separation of concerns
- Independent evolution and deployment
- Technology-agnostic API contract

## Why Spring Security?

Spring Security provides:
- Mature authentication abstractions
- Integration with PasswordEncoder
- Fine-grained endpoint protection

## Why PostgreSQL?

PostgreSQL was selected for its reliability,
strong consistency guarantees and widespread industry adoption.

## Why Limited Scope?

The project intentionally focuses on authentication to:
- Avoid premature complexity
- Emphasize security and correctness
- Serve as a reusable foundation for future features

## Why Booking Belongs to Provider?

Bookings are tied to the provider’s availability and schedule.
Conflict detection must be scoped per provider.
This aligns with real-world scheduling systems.

## Why OffsetDateTime Instead of LocalDate + LocalTime?

Using a single timestamp simplifies:
- Conflict detection
- Indexing
- Timezone handling
- Range queries

Date/time separation is handled at presentation layer.

## Why startAt + duration Instead of startAt + endAt?

Duration is part of the business concept.
End time is derived data.
Storing only essential attributes avoids redundancy and inconsistent states.

## Why Combine Application-Level and Database-Level Conflict Protection?

Application layer provides business validation and meaningful error messages.
Database layer ensures consistency under concurrent requests.
This prevents race conditions.

## Why Modular Monolith Instead of Microservices?

At the current scale and scope, a modular monolith provides:

- Simpler deployment
- Strong consistency guarantees
- Reduced operational overhead
- Faster iteration

Microservices would introduce unnecessary complexity without clear scaling requirements.