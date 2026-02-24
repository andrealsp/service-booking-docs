# Scalability Considerations

Although the current scope does not require high throughput, the architecture was designed with scalability in mind.

## Horizontal Scalability

- Stateless JWT authentication
- No server-side session storage
- Modular monolith allowing internal domain separation

## Database Considerations

- Provider-scoped indexing strategy
- Conflict detection optimized for range queries
- Future potential for read replicas

## Future Scaling Path

If booking traffic grows significantly:

- Introduce read/write separation
- Consider caching for availability queries
- Evaluate extraction of booking domain into independent service if required