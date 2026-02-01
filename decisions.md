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
