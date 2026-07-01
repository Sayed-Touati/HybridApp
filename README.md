# HybridApp - Expense Tracker

HybridApp is an in-progress expense tracking application built with a mobile-first architecture. The project is designed to help users record income and expenses, track transaction history, and view a financial summary from a dedicated backend API.

The app is currently under development, with the backend API structure already focused on transaction management and financial summaries.

## Status

🚧 **In Progress**

## Tech Stack

### Mobile

- React Native
- Expo
- Expo Router
- React Navigation

### Backend

- Node.js
- Express.js
- Neon Serverless PostgreSQL
- Upstash Redis
- REST API

## Features

- Create income and expense transactions
- Store transaction title, amount, category, and user ID
- Fetch transactions by user
- Delete transactions
- Calculate financial summary:
  - Balance
  - Income
  - Expenses
- Rate limiting with Upstash Redis
- Serverless PostgreSQL database with Neon

## Project Structure

```txt
HybridApp/
├── Backend/
│   ├── src/
│   │   ├── config/
│   │   │   ├── db.js
│   │   │   └── upstach.js
│   │   ├── controllers/
│   │   │   └── transactionsContoller.js
│   │   ├── Middleware/
│   │   │   └── rateLimiter.js
│   │   ├── routes/
│   │   │   └── transactionsRoute.js
│   │   └── server.js
│   └── package.json
│
└── Mobile/
    ├── app/
    ├── assets/
    ├── components/
    ├── constants/
    ├── lib/
    └── package.json
```

## API Endpoints

Base route:

```txt
/api/transactions
```

### Get Transactions By User

```http
GET /api/transactions/:userId
```

Returns all transactions for a specific user, ordered by creation date.

### Create Transaction

```http
POST /api/transactions
```

Request body:

```json
{
  "user_id": "user123",
  "title": "Salary",
  "amount": 1200,
  "category": "Income"
}
```

### Delete Transaction

```http
DELETE /api/transactions/:id
```

Deletes a transaction by ID.

### Get User Summary

```http
GET /api/transactions/summary/:userId
```

Returns:

```json
{
  "balance": "1000.00",
  "income": "1500.00",
  "expenses": "-500.00"
}
```

## Getting Started

### Backend Setup

Go to the backend folder:

```bash
cd Backend
```

Install dependencies:

```bash
npm install
```

Create a `.env` file:

```env
PORT=5001
DATABASE_URL=your_neon_database_url
UPSTASH_REDIS_REST_URL=your_upstash_redis_url
UPSTASH_REDIS_REST_TOKEN=your_upstash_redis_token
```

Start the development server:

```bash
npm run dev
```

### Mobile Setup

Go to the mobile folder:

```bash
cd Mobile
```

Install dependencies:

```bash
npm install
```

Start the Expo app:

```bash
npm start
```

Then open the app using:

- Expo Go
- Android emulator
- iOS simulator
- Web preview

## Roadmap

- Build the full mobile expense tracking interface
- Add transaction creation and deletion screens
- Connect the mobile app to the backend API
- Add charts and visual spending insights
- Improve category-based expense tracking
- Add authentication and user-specific sessions
- Polish the UI for Android and iOS

## About

This project is part of my journey building mobile-first applications with React Native, Expo, and backend APIs. The goal is to create a practical expense tracker that combines clean mobile UX with a reliable transaction management backend.
