# Security Model

## Authentication Strategy

The system uses JWT-based stateless authentication.
Tokens are issued upon successful login and validated on each request.

## Password Handling

- Passwords are never stored in plain text
- Hashing is performed using Spring Security PasswordEncoder
- Raw credentials are only used transiently during authentication

## Token Handling

- Tokens include expiration time
- Invalid or expired tokens are rejected
- Token validation is applied at filter level

## Frontend Considerations

- Tokens are stored client-side
- No sensitive data is persisted beyond the token
- Token validation occurs during navigation

## Known Trade-offs

- Token revocation is not implemented
- Refresh tokens are not part of current scope
