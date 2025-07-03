# Express.js + PostgreSQL CRUD API

## Objective
Create a simple Express.js API that connects to a PostgreSQL database and performs basic CRUD operations.

---

## Requirements
✅ Working Express.js server  
✅ PostgreSQL database connection  
✅ All CRUD operations (Create, Read, Update, Delete)  
✅ Basic error handling  
✅ Testable via Postman or similar tools

---

## Setup Instructions

### 1. Install PostgreSQL and Node.js
Ensure PostgreSQL and Node.js are installed on your machine.

### 2. Create a PostgreSQL Database
Run the following SQL in your PostgreSQL client:
```sql
CREATE TABLE users (
  id SERIAL PRIMARY KEY,
  name VARCHAR(100),
  email VARCHAR(100),
  age INTEGER
);
```

### 3. Install dependencies
```bash
npm init -y
npm install express pg
```

### 4. Configure PostgreSQL connection
Update the `Pool` settings in `index.js`:
```js
const pool = new Pool({
  user: 'your_username',
  host: 'localhost',
  database: 'your_database',
  password: 'your_password',
  port: 5432,
});
```

### 5. Run the server
```bash
node index.js
```

Server will run at: `http://localhost:3000`

---

## API Endpoints

### GET `/users`
Returns all users

### GET `/users/:id`
Returns a specific user

### POST `/users`
Creates a new user  
**Body:**
```json
{
  "name": "John Doe",
  "email": "john@example.com",
  "age": 30
}
```

### PUT `/users/:id`
Updates a user  
**Body:**
```json
{
  "name": "Jane Doe",
  "email": "jane@example.com",
  "age": 28
}
```

### DELETE `/users/:id`
Deletes a user

---

## Testing
Use Postman or Curl to test the above endpoints.
