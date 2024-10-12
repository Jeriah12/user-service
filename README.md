# User Service

The **User Service** is a microservice responsible for managing user-related operations such as registration, authentication, and profile management in the e-commerce platform.

## Table of Contents

- [Features](#features)
- [Technology Stack](#technology-stack)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Environment Variables](#environment-variables)
- [Running the Service](#running-the-service)
- [API Endpoints](#api-endpoints)
- [Testing](#testing)
- [Contributing](#contributing)
- [License](#license)

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

3. **Environment VariablesInstall Dependencies:**
   Create a .env file in the root directory and add the following environment variables:
   ```dotenv
   PORT=3000
   MONGO_URI=mongodb://localhost:27017/userdb
   JWT_SECRET=your_jwt_secret_key


