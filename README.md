# API_login_jwtToken_mongodb
This is a RESTful API for user login implemented using Node.js, jsonwebtoken (JWT token validation), and Mongoose.

## Features

- User registration
- User authentication
- JWT token generation and validation
- Secure storage of user credentials using MongoDB


## Getting Started

#### 1. Clone the repository:
- git clone [https://github.com/theiv767/API_login_jwtToken_mongodb](https://github.com/theiv767/API_login_jwtToken_mongodb)

#### 2. Install dependencies:
- npm install

#### 3. Configure environment variables:
Create a `.env` file in the root directory and provide the following variables:

- SERVER_PORT = `port`
- URL_DB = `your db endpoint`
- SECRET = `some hash code`

#### 4. Start the server:
- npm start

## API Endpoints

### User Registration

- `POST /users/auth/register/`
  - Request Body:
    - `username` : User's username
	 - `email`: User's email
	 - `password`: User's password
	 - `confirmPassword`: User's password
	  
  - Response:
    - Status: 200 OK

### User Login

- `POST /users/auth/login/`
  - Request Body:
    - `email`: User's email
    - `password`: User's password
    
  - Response:
    - Status: 200 OK
    - `message`: "Login efetuado com sucesso"
	 - `id`: User's password
    - `token`: JWT token for authentication

### Protected Route

- `GET /users/:id`
  - Request Header:
    - `Authorization`: Bearer {token}
  - Response:
    - Status: 200 OK
    - `message`: Success!
