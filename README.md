# User Service

The **User Service** is a microservice responsible for managing user-related operations such as registration, authentication, and profile management in the e-commerce platform.

## Table of Contents

- [Features](#features)
- [Technology Stack](#technology-stack)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [API Endpoints](#api-endpoints)
- [Testing](#testing)


## Features

- **User Registration:** Allows new users to create an account.
- **User Authentication (JWT):** Provides secure authentication using JSON Web Tokens.
- **User Profile Management:** Enables users to view and update their profile information.
- **Password Hashing and Validation:** Ensures user passwords are securely stored and validated.

## Technology Stack

- **Language:** Node.js
- **Framework:** Express.js
- **Database:** MongoDB
- **Authentication:** JSON Web Tokens (JWT)
- **Containerization:** Docker (optional)

## Prerequisites

Before you begin, ensure you have met the following requirements:

- **Node.js** v14.x or higher
- **npm** v6.x or higher
- **MongoDB** v4.x or higher
- **Docker** (optional, for containerization)
- **Git** for version control

## Installation

Follow these steps to set up the User Service on your local machine:

1. **Clone the repository:**

   ```bash
   git clone https://github.com/your-username/user-service.git
   cd user-service
   
2. **Install Dependencies:**

   ```bash
   npm install

3. **Environment Variables:**

    Create a .env file in the root directory and add the following environment variables:
   ```dotenv
   PORT=3000
   MONGO_URI=mongodb://localhost:27017/userdb
   JWT_SECRET=your_jwt_secret_key
   ```

   * PORT: The port number on which the service will run (default is 3000).
   * MONGO_URI: MongoDB connection string (update with your MongoDB credentials if necessary).
   * JWT_SECRET: A secret key for signing JWT tokens (replace your_jwt_secret_key with a strong secret).

 4. **Running Docker:**
    
    Build the docker image
    ```bash
    docker build -t user-service:latest .
    ```

    Run the Docker container
    ```bash
    docker run -p 3000:3000 --env-file .env user-service:latest
    ```

    The service should now be accessible at http://localhost:3000

## API Endpoints

   ### Register a new user
   * Endpoint: POST /api/v1/auth/register   
   * Description: Creates a new user account.  
   * Request Body:
   
   ```json
   {
     "username": "johndoe",
     "email": "johndoe@example.com",
     "password": "your_password"
   }
   ```

   ### User login
   * Endpoint: POST /api/v1/auth/login
   * Description: Authenticates a user and returns a JWT token.
   * Request Body:
     
   ```json
   {
     "email": "johndoe@example.com",
     "password": "your_password"
   }
   ```

   ### User Profile
   * Get user profile
   * Endpoint: GET /api/v1/users/profile
   * Description: Retrieves the authenticated user's profile.
   * Headers:
     
   ```makefile
   Authorization: Bearer <JWT_TOKEN>
   ```

   ### Update user profile
   * Endpoint: PUT /api/v1/users/profile
   * Description: Updates the authenticated user's profile information.
   * Headers:
   ```makefile
   Authorization: Bearer <JWT_TOKEN>
   ```
   * Request Body (example):
   ```json
   {
     "username": "john_doe_updated",
     "email": "newemail@example.com"
   }
   ```
## Testing
Run unit tests using:
```bash
npm test
```
This command will execute all tests located in the tests directory.
