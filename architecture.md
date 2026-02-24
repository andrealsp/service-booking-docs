# System Architecture

## High-Level Architecture

The platform follows a client–server architecture composed of:

- React-based frontend (Service Booking UI)
- Spring Boot backend (Service Booking API)
- PostgreSQL relational database

Communication is performed via REST APIs using JSON payloads
and JWT-based authentication.

## Component Overview

### Frontend (Service Booking UI)

- Handles user interaction
- Manages authentication state
- Stores JWT token client-side
- Performs token validation during navigation

### Backend (Service Booking API)

- Manages user lifecycle
- Handles authentication and token issuance
- Validates JWT on protected endpoints
- Persists user data in PostgreSQL

### Database

- Stores user credentials and metadata
- Passwords are stored in hashed form only

## Authentication Flow (Simplified)

1. User submits credentials via frontend
2. Backend authenticates user
3. JWT token is issued
4. Frontend stores token
5. Subsequent requests include Authorization header

## Upcoming Domain Architecture

The booking domain will introduce the following core components:

- Provider (1:1 relationship with User)
- Availability (provider working hours)
- Booking (startAt + duration model)

Time modeling decision:
- OffsetDateTime used for scheduling
- Duration stored explicitly as part of business concept
- End time derived from startAt + duration

Conflict handling strategy:
- Application-level validation
- Database-level protection against overlapping bookings

## Architectural Style

The platform follows a modular monolith architecture.

Domains are separated logically within the same deployment unit,
allowing clear bounded contexts while keeping operational complexity low.

This approach was intentionally chosen to:
- Simplify deployment
- Avoid premature microservice complexity
- Maintain strong transactional consistency
- Enable future extraction if scaling demands it