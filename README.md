# Stock Trading Platform

A modern stock trading dashboard backend built with Node.js, Express.js, and MongoDB. This project provides secure user authentication, portfolio tracking, and order management APIs for a trading application.

## Overview

This repository contains the server-side application for a stock trading platform. It supports:

- User signup and login
- JWT-based authentication with secure cookie storage
- Portfolio holdings and position tracking
- Order creation and retrieval
- MongoDB persistence with Mongoose models and schemas
- CORS-enabled API for browser-based clients

The application is designed to act as the backend layer for a trading dashboard and can be connected to a frontend application or admin panel.

## Tech Stack

- Node.js
- Express.js
- MongoDB
- Mongoose
- JWT (jsonwebtoken)
- bcryptjs
- dotenv
- CORS
- Cookie parsing
- Nodemon (development)

## Project Structure

```text
stock_trading/
├── backend/
│   ├── controller/
│   │   └── AuthController.js
│   ├── middleware/
│   │   └── AuthMiddleware.js
│   ├── model/
│   │   ├── HoldingModel.js
│   │   ├── OrderModel.js
│   │   ├── PositionModel.js
│   │   └── UserModel.js
│   ├── routes/
│   │   └── AuthRoute.js
│   ├── schemas/
│   │   ├── HoldingSchema.js
│   │   ├── OrderSchema.js
│   │   ├── PositionSchema.js
│   │   └── UserSchema.js
│   ├── util/
│   │   └── SecretToken.js
│   ├── .env
│   ├── index.js
│   ├── package.json
│   └── package-lock.json
├── .gitignore
├── README.md
└── (additional frontend/dashboard assets may be added separately)
```

## Features

### Authentication
- User registration with email, username, and password
- Login with password verification using bcrypt
- JWT generation and cookie-based session handling
- User verification endpoint for protected routes

### Portfolio Management
- Fetch all holdings
- Retrieve all positions
- Store and manage trading orders

### API Layer
- Express REST endpoints for authentication and trading data
- JSON request/response handling
- CORS configuration for local frontend development

## Getting Started

### Prerequisites

- Node.js (v18 or later recommended)
- MongoDB instance or MongoDB Atlas connection
- npm or yarn

### Installation

1. Clone the repository:

```bash
git clone https://github.com/himanshupant23/stock_trading.git
cd stock_trading/backend
```

2. Install dependencies:

```bash
npm install
```

3. Create a `.env` file in the `backend` directory with the following variables:

```env
PORT=3002
MONGO_URL=mongodb://localhost:27017/stock_trading
TOKEN_KEY=your_secure_jwt_secret
```

4. Start the server:

```bash
npm start
```

The server will start on the configured port and connect to MongoDB automatically.

## Environment Variables

| Variable | Description |
| --- | --- |
| `PORT` | Port used by the Express server |
| `MONGO_URL` | MongoDB connection string |
| `TOKEN_KEY` | Secret key used for JWT generation and verification |

## API Endpoints

### Authentication

- `POST /auth/signup` — Register a new user
- `POST /auth/login` — Log in an existing user
- `POST /auth/verify` — Verify the current user from the token

### Trading Data

- `GET /allHoldings` — Fetch all portfolio holdings
- `GET /allOrders` — Fetch all orders
- `GET /allPositions` — Fetch all positions
- `POST /newOrders` — Create a new order

## Example Request

### Sign Up

```bash
curl -X POST http://localhost:3002/auth/signup \
  -H "Content-Type: application/json" \
  -d '{
    "username": "demouser",
    "email": "demo@example.com",
    "password": "securepassword123"
  }'
```

### Login

```bash
curl -X POST http://localhost:3002/auth/login \
  -H "Content-Type: application/json" \
  -d '{
    "email": "demo@example.com",
    "password": "securepassword123"
  }'
```

## Notes

- This repository currently focuses on the backend services for the stock trading application.
- Frontend or dashboard assets may be maintained in a separate module or as a different repository depending on the deployment setup.
- Sensitive environment values such as JWT secrets and database credentials should never be committed to source control.

## License

This project does not currently declare an explicit license in the repository metadata. Please check the repository settings or project documentation for licensing details.

## Contact

For questions or collaboration, visit the repository owner: https://github.com/himanshupant23
