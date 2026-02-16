# Walksy Backend API

Express.js + MongoDB backend for the Walksy application.

## Tech Stack

- Node.js
- Express.js v5
- MongoDB with Mongoose
- JWT Authentication
- Bcrypt for password hashing

## Setup

1. Install dependencies:
```bash
npm install
```

2. Create `.env` file:
```env
NODE_ENV=development
PORT=5000
MONGO_URI=mongodb://localhost:27017/walksy
# Or your MongoDB Atlas URI
JWT_SECRET=your_super_secret_key_123
```

3. Run the server:
```bash
npm start
```

## API Endpoints

### Authentication
- `POST /api/users` - Register new user
- `POST /api/users/login` - Login user
- `GET /api/users/profile` - Get user profile (Protected)

### Tasks
- `POST /api/tasks` - Create new task
- `GET /api/tasks/nearby` - Get nearby tasks
- `PUT /api/tasks/:id/accept` - Accept a task
- `PUT /api/tasks/:id/complete` - Complete a task

### Transactions
- `GET /api/transactions` - Get user transactions

## Project Structure

```
backend/
├── config/
│   └── db.js           # MongoDB connection
├── controllers/
│   ├── userController.js
│   ├── taskController.js
│   └── transactionController.js
├── middleware/
│   ├── authMiddleware.js
│   └── errorMiddleware.js
├── models/
│   ├── userModel.js
│   ├── taskModel.js
│   └── transactionModel.js
├── routes/
│   ├── userRoutes.js
│   ├── taskRoutes.js
│   └── transactionRoutes.js
├── utils/
│   └── generateToken.js
├── .env
├── .gitignore
├── package.json
└── server.js           # Entry point
```

## Deployment

### Deploy to Render/Railway

1. Push code to GitHub (already done)
2. Connect your GitHub repository to Render/Railway
3. Set environment variables:
   - `MONGO_URI` - Your MongoDB connection string
   - `JWT_SECRET` - Your JWT secret key
   - `NODE_ENV` - Set to `production`
4. Set build command: `npm install`
5. Set start command: `npm start`

## Environment Variables

| Variable | Description | Example |
|----------|-------------|---------|
| `NODE_ENV` | Environment mode | `development` or `production` |
| `PORT` | Server port | `5000` |
| `MONGO_URI` | MongoDB connection string | `mongodb://localhost:27017/walksy` |
| `JWT_SECRET` | Secret for JWT tokens | `your_secret_key_here` |

## CORS Configuration

The backend allows CORS from all origins by default. For production, update the CORS configuration in `server.js` to only allow your frontend domain.
