# User Management API

This is a simple RESTful API built with **Node.js**, **Express.js**, and **MongoDB** for user registration, login, and profile management. It demonstrates authentication using **JWT (JSON Web Token)** and password hashing with **bcryptjs**.

## Features

- **User Registration**: Users can register by providing their name, email, and password.
- **User Login**: Users can log in by providing their email and password.
- **Protected Route**: Only authenticated users with a valid JWT can access their profile.
- **Password Hashing**: User passwords are securely hashed using bcryptjs before being stored in the database.
- **JWT Authentication**: After login, a JWT token is issued, which can be used to authenticate future requests.

## Technologies Used

- **Node.js**: JavaScript runtime for building the API
- **Express.js**: Web framework for building RESTful APIs
- **MongoDB**: NoSQL database for storing user data
- **Mongoose**: MongoDB ODM (Object Data Modeling) library for Node.js
- **bcryptjs**: Library for hashing passwords securely
- **jsonwebtoken (JWT)**: Used for user authentication through JSON Web Tokens
- **dotenv**: For managing environment variables
- **Postman**: Used for testing API routes

## Getting Started

### Prerequisites

- **Node.js**: You need to have Node.js installed on your machine.
- **MongoDB**: You need MongoDB running locally or remotely. If you don’t have MongoDB installed, you can [download MongoDB](https://www.mongodb.com/try/download/community) or use [MongoDB Atlas](https://www.mongodb.com/cloud/atlas) for a cloud-based solution.

### Installation

1. Clone this repository:
   ```bash
   git clone https://github.com/saifeldeen911/user-api.git
   cd user-api
   ```


2. Install dependencies:

   ```bash
   npm install
   ```

3. Create a `.env` file in the root of the project and add your environment variables:

   ```env
   PORT=5000
   MONGO_URI=mongodb://127.0.0.1:27017/user_api
   JWT_SECRET=your_secret_key
   ```

4. Start the application:

   ```bash
   npm run dev
   ```

   The API will be running at `http://localhost:5000`.

## API Endpoints

### 1. **POST** `/api/users/register`

- **Description**: Register a new user
- **Request Body**:
  ```json
  {
    "name": "Saif",
    "email": "saif@example.com",
    "password": "123456"
  }
  ```
- **Response**:
  ```json
  {
    "msg": "User registered",
    "user": {
      "_id": "user_id",
      "name": "Saif",
      "email": "saif@example.com"
    }
  }
  ```

### 2. **POST** `/api/users/login`

- **Description**: Login with email and password
- **Request Body**:
  ```json
  {
    "email": "saif@example.com",
    "password": "123456"
  }
  ```
- **Response**:
  ```json
  {
    "token": "jwt_token_here"
  }
  ```

### 3. **GET** `/api/users/profile`

- **Description**: Get the profile of the logged-in user (requires authentication)
- **Headers**:
  - `Authorization: Bearer <your_jwt_token>`
- **Response**:
  ```json
  {
    "_id": "user_id",
    "name": "Saif",
    "email": "saif@example.com"
  }
  ```

## Testing with Postman

1. **Register a User**: Use the `/api/users/register` endpoint to create a new user.
2. **Login**: After registration, use `/api/users/login` to get the JWT token.
3. **Profile**: Use `/api/users/profile` with the token in the Authorization header to fetch the user profile.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

## Author

- **Saifeldeen khalaf**
- **GitHub**: [@saifeldeen911](https://github.com/saifeldeen911)
- **LinkedIn**: [Saifeldeen Mohamed Khalaf](https://www.linkedin.com/in/saifeldeen-mohamed-khalaf/)

```
