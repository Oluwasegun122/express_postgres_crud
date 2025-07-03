# Express.js + PostgreSQL CRUD API (Refactored)

## Features
- Secure `.env` configuration
- Separated routes, controllers, middleware, and config
- Input validation
- Clean project structure

## Setup

### 1. Clone the project and install dependencies
```bash
npm install express pg dotenv
```

### 2. Create `.env` file based on `.env.example`
```env
DB_USER=your_username
DB_HOST=localhost
DB_NAME=your_database
DB_PASSWORD=your_password
DB_PORT=5432
PORT=3000
```

### 3. Create the database table
```sql
CREATE TABLE users (
  id SERIAL PRIMARY KEY,
  name VARCHAR(100),
  email VARCHAR(100),
  age INTEGER
);
```

### 4. Run the server
```bash
node src/index.js
```

## API Endpoints
- `GET /users` – Get all users
- `GET /users/:id` – Get user by ID
- `POST /users` – Create user (requires `name`, `email`, `age`)
- `PUT /users/:id` – Update user (requires `name`, `email`, `age`)
- `DELETE /users/:id` – Delete user

## Input Validation
All POST and PUT requests are validated to ensure:
- `name` and `email` are non-empty
- `age` is a number

## Folder Structure
```
src/
├── config/
│   └── db.js
├── controllers/
│   └── userController.js
├── routes/
│   └── userRoutes.js
├── middlewares/
│   └── validateUser.js
└── index.js
```
