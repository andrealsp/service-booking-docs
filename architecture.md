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
