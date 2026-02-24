# API Contracts

## Authentication

### POST /auth/register

Registers a new user.

**Request Body**
- username
- email
- password
- name
- role

**Responses**
- 201 Created
- 400 Username or email already exists

---

### POST /auth/login

Authenticates a user and returns a JWT token.

**Request Body**
- identifier (username or email)
- password

**Response**
- token (Bearer JWT)
- 404 User not found
- 401 Invalid password

---

### GET /auth/validate

Validates token integrity and expiration.

**Headers**
- Authorization: Bearer <JWT_TOKEN>

**Response**
- 200 OK (valid)
- 400 Token must not be empty.
- 401 Token expired, Invalid token format or signature.
- 500 Error while validating token.

