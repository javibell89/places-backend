# Places Backend API

A RESTful API backend service for managing places and users, built with Node.js and Express.

## Features

- User authentication and authorization
- CRUD operations for places
- User management
- File upload support for images
- Location utilities
- Secure password handling
- JWT-based authentication

## Technologies

- Node.js
- Express.js
- MongoDB with Mongoose
- JSON Web Tokens (JWT)
- bcryptjs for password hashing
- Express Validator for input validation
- Multer for file uploads
- Axios for external API requests
- dotenv for environment variables

## Prerequisites

- Node.js (v12 or higher)
- MongoDB instance
- npm or yarn package manager

## Installation

1. Clone the repository
2. Install dependencies:

```bash
npm install
```

3. Create a `.env` file in the root directory with the following variables:

```
MONGODB_URI=your_mongodb_connection_string
JWT_SECRET=your_jwt_secret_key
```

## Running the Application

Development mode with auto-reload:

```bash
npm start
```

## Project Structure

```
├── controllers/
│   ├── places-controllers.js    # Place-related operations
│   └── users-controllers.js     # User management operations
├── middleware/
│   ├── check-auth.js           # JWT authentication middleware
│   └── file-upload.js          # File upload handling
├── models/
│   ├── http-error.js           # Custom error handling
│   ├── place.js                # Place data model
│   └── user.js                 # User data model
├── routes/
│   ├── places-routes.js        # Place endpoints
│   └── users-routes.js         # User endpoints
└── utils/
    └── location.js             # Location-related utilities
```

## API Endpoints

### Places

- GET /api/places/:pid - Get a place by ID
- GET /api/places/user/:uid - Get places by user ID
- POST /api/places - Create a new place
- PATCH /api/places/:pid - Update a place
- DELETE /api/places/:pid - Delete a place

### Users

- GET /api/users - Get list of users
- POST /api/users/signup - Create new user account
- POST /api/users/login - Login user

## Authentication

The API uses JWT (JSON Web Tokens) for authentication. Protected routes require a valid JWT token in the Authorization header:

```
Authorization: Bearer <your_jwt_token>
```

## File Upload

The API supports file uploads for images using Multer middleware. Uploaded files are stored in the `/uploads` directory.

## Error Handling

The application uses a custom error handling model (http-error.js) for consistent error responses across the API.

## License

ISC
