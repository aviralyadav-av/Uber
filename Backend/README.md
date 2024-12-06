# User Authentication Endpoints

## User Registration Endpoint

### Endpoint
`POST /users/register`

### Description
This endpoint allows a new user to register by providing their email, password, and full name. Upon successful registration, a JSON Web Token (JWT) is generated and returned, which can be used for authentication in subsequent requests.

### Request Body
The request body must be in JSON format and should contain the following fields:

- `fullname`: An object containing the user's full name.
  - `firstname`: (string, required) The first name of the user. Must be at least 3 characters long.
  - `lastname`: (string, optional) The last name of the user. Must be at least 3 characters long if provided.
- `email`: (string, required) The email address of the user. Must be a valid email format and at least 5 characters long.
- `password`: (string, required) The password for the user account. Must be at least 6 characters long.

#### Example Request
```json
{
  "fullname": {
    "firstname": "John",
    "lastname": "Doe"
  },
  "email": "john.doe@example.com",
  "password": "securePassword123"
}
```

---

## User Login Endpoint

### Endpoint
`POST /users/login`

### Description
This endpoint allows an existing user to log in by providing their email and password. Upon successful login, a JSON Web Token (JWT) is generated and returned, which can be used for authentication in subsequent requests.

### Request Body
The request body must be in JSON format and should contain the following fields:

- `email`: (string, required) The email address of the user. Must be a valid email format and at least 5 characters long.
- `password`: (string, required) The password for the user account. Must be at least 6 characters long.

#### Example Request
```json
{
  "email": "john.doe@example.com",
  "password": "securePassword123"
}
