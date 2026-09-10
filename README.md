# Airbnb Starter - Full Stack MERN Application

A full-stack Airbnb clone application built with **MongoDB**, **Express.js**, **React**, and **Node.js** (MERN stack).

---

## 📋 Table of Contents

- [Project Overview](#project-overview)
- [Tech Stack](#tech-stack)
- [Project Structure](#project-structure)
- [Installation & Setup](#installation--setup)
- [Configuration](#configuration)
- [Running the Application](#running-the-application)
- [API Endpoints](#api-endpoints)
- [Features](#features)
- [Troubleshooting](#troubleshooting)
- [Recent Bug Fixes](#recent-bug-fixes)

---

## 🎯 Project Overview

This is a full-stack Airbnb clone application that demonstrates modern web development practices using the MERN stack. The application allows users to browse properties, manage listings, and handle user authentication.

**Fork of:** [rishavchanda/airbnb-starter](https://github.com/rishavchanda/airbnb-starter)

---

## 🛠 Tech Stack

### Backend
- **Runtime:** Node.js
- **Framework:** Express.js 4.19.2
- **Database:** MongoDB 6.7.0
- **ODM:** Mongoose 8.4.1
- **Authentication:** JWT (jsonwebtoken 9.0.2)
- **Password Hashing:** bcrypt 5.1.1
- **CORS:** cors 2.8.5
- **Dev Tools:** nodemon 3.1.3

### Frontend
- **Library:** React 18.3.1
- **UI Framework:** Material-UI (MUI) 5.16.5
- **State Management:** Redux Toolkit 2.2.5
- **Routing:** React Router DOM 6.23.1
- **HTTP Client:** Axios 1.7.2
- **Styling:** Styled Components 6.1.12
- **Date Handling:** date-fns, dayjs, moment, luxon

---

## 📁 Project Structure

```
airbnb-starter/
├── client/                          # React Frontend
│   ├── public/                      # Static assets
│   ├── src/                         # React components & logic
│   ├── package.json                 # Frontend dependencies
│   └── package-lock.json
│
├── server/                          # Express Backend
│   ├── routes/
│   │   ├── user.js                 # User authentication & profile routes
│   │   └── properties.js           # Property listing routes
│   ├── controllers/                # Business logic (TODO)
│   ├── models/                     # Mongoose schemas (TODO)
│   ├── middlewares/                # Custom middleware (TODO)
│   ├── index.js                    # Express app entry point
│   ├── error.js                    # Error handling
│   ├── .env.example                # Environment template
│   ├── package.json                # Backend dependencies
│   └── package-lock.json
│
├── .gitignore                       # Git ignore rules
└── README.md                        # This file
```

---

## 🚀 Installation & Setup

### Prerequisites

Before you begin, ensure you have the following installed:
- **Node.js** (v14 or higher) - [Download](https://nodejs.org/)
- **npm** or **yarn** package manager
- **MongoDB** account - [Create Free Cluster](https://www.mongodb.com/cloud/atlas)
- **Git**

### Step 1: Clone the Repository

```bash
git clone https://github.com/saitejareddy100/airbnb-starter.git
cd airbnb-starter
```

### Step 2: Install Backend Dependencies

```bash
cd server
npm install
```

### Step 3: Install Frontend Dependencies

```bash
cd ../client
npm install
```

---

## ⚙️ Configuration

### Step 1: Setup MongoDB

1. Go to [MongoDB Atlas](https://www.mongodb.com/cloud/atlas)
2. Create a new cluster
3. Create a database user with read/write permissions
4. Get your connection string (looks like: `mongodb+srv://username:password@cluster.mongodb.net/`)

### Step 2: Configure Environment Variables

Navigate to the `server` directory and create a `.env` file:

```bash
cd server
cp .env.example .env
```

Edit `.env` and add your credentials:

```env
# MongoDB Connection URL
MONGODB_URL="mongodb+srv://your_username:your_password@your_cluster.mongodb.net/?retryWrites=true&w=majority"

# JWT Secret Key (generate a strong random string)
# Option 1: Use Node.js to generate
# node -e "console.log(require('crypto').randomBytes(32).toString('hex'))"
JWT="your_generated_secret_key_here"
```

### Step 3: Generate JWT Secret (Optional but Recommended)

For enhanced security, generate a strong JWT secret:

```bash
node -e "console.log(require('crypto').randomBytes(32).toString('hex'))"
```

Copy the output and paste it as your `JWT` value in `.env`

### Security Notes ⚠️

- **NEVER** commit `.env` file to version control
- `.gitignore` prevents this automatically
- Keep your MongoDB credentials confidential
- Rotate credentials periodically
- Use strong, complex JWT secrets

---

## ▶️ Running the Application

### Option 1: Run Backend and Frontend Separately (Development)

**Terminal 1 - Backend:**
```bash
cd server
npm start
# Server runs on http://localhost:8080
```

**Terminal 2 - Frontend:**
```bash
cd client
npm start
# Frontend runs on http://localhost:3000
```

### Option 2: Backend Only

If you only want to run the backend:

```bash
cd server
npm start
```

Visit: `http://localhost:8080` - You should see "Smart Contract Analyzer Backend Running"

### Common Issues

**Port already in use:**
```bash
# Kill process using port 8080
lsof -ti:8080 | xargs kill -9  # macOS/Linux
netstat -ano | findstr :8080   # Windows (then taskkill /PID <PID> /F)
```

**MongoDB connection failed:**
- Verify `MONGODB_URL` in `.env`
- Check MongoDB cluster is active
- Ensure IP whitelist includes your machine in MongoDB Atlas

---

## 🔌 API Endpoints

### User Routes (`/api/users`)

| Method | Endpoint | Description | Status |
|--------|----------|-------------|--------|
| POST | `/api/users/register` | Register new user | 🔨 TODO |
| POST | `/api/users/login` | User login | 🔨 TODO |
| GET | `/api/users/profile` | Get user profile | 🔨 TODO |
| PUT | `/api/users/profile` | Update user profile | 🔨 TODO |
| POST | `/api/users/logout` | User logout | 🔨 TODO |

### Property Routes (`/api/properties`)

| Method | Endpoint | Description | Status |
|--------|----------|-------------|--------|
| GET | `/api/properties` | Get all properties | 🔨 TODO |
| GET | `/api/properties/:id` | Get property by ID | 🔨 TODO |
| POST | `/api/properties` | Create new property | 🔨 TODO |
| PUT | `/api/properties/:id` | Update property | 🔨 TODO |
| DELETE | `/api/properties/:id` | Delete property | 🔨 TODO |
| GET | `/api/properties/search` | Search properties | 🔨 TODO |

---

## ✨ Features

### Current Features
- ✅ Express server setup with CORS enabled
- ✅ MongoDB connection via Mongoose
- ✅ Environment configuration system
- ✅ Error handling middleware
- ✅ React frontend with Material-UI
- ✅ Redux state management
- ✅ React Router for navigation

### Planned Features (To Implement)
- 🔨 User authentication (register, login, logout)
- 🔨 JWT-based authorization
- 🔨 Property CRUD operations
- 🔨 Property search and filtering
- 🔨 User profiles and favorites
- 🔨 Booking system
- 🔨 Reviews and ratings
- 🔨 Image upload for properties

---

## 🐛 Troubleshooting

### Backend Issues

**Error: "Cannot find module 'cors'"**
```bash
# Solution: Reinstall dependencies
cd server
rm -rf node_modules package-lock.json
npm install
```

**Error: "MONGODB_URL is not defined"**
```bash
# Solution: Check .env file exists and has correct format
cd server
ls -la .env  # Verify file exists
cat .env    # Check content
```

**Error: "Failed to connect with mongo"**
- Verify MongoDB cluster is running in Atlas
- Check connection string syntax
- Ensure IP whitelist includes your IP (check in MongoDB Atlas → Security → Network Access)

### Frontend Issues

**npm ERR! code ERESOLVE**
```bash
# Solution: Use legacy peer deps flag
npm install --legacy-peer-deps
```

**Port 3000 already in use**
```bash
# Solution: Use different port
PORT=3001 npm start
```

### CORS Errors

If you see CORS errors in browser console:
- Ensure backend is running on port 8080
- Check frontend is making requests to `http://localhost:8080`
- Verify CORS is enabled in `server/index.js`

---

## 📝 Recent Bug Fixes (Sep 10, 2026)

### ✅ Commit: 6e619b66

**Issues Fixed:**

1. **Routes Not Registered** - Added `app.use()` middleware for user and property routes
2. **Missing Route Files** - Created `server/routes/user.js` and `server/routes/properties.js`
3. **No .gitignore** - Added `.gitignore` to prevent committing node_modules and sensitive files
4. **No .env.example** - Added `.env.example` template for environment setup

**Changes Made:**
```
✅ Added .gitignore
✅ Added server/.env.example
✅ Fixed server/index.js (registered routes)
✅ Created server/routes/user.js
✅ Created server/routes/properties.js
```

---

## 📖 Development Guide

### Adding New Routes

**1. Create route file in `server/routes/`:**

```javascript
// server/routes/bookings.js
import express from "express";
const router = express.Router();

// TODO: Implement booking routes
// - GET / - Get all bookings
// - POST / - Create new booking
// - DELETE /:id - Cancel booking

export default router;
```

**2. Register route in `server/index.js`:**

```javascript
import BookingRoutes from "./routes/bookings.js";

// Add to middleware
app.use("/api/bookings", BookingRoutes);
```

### Adding Controllers

**1. Create controller file in `server/controllers/`:**

```javascript
// server/controllers/userController.js
export const registerUser = async (req, res) => {
  // Implement registration logic
};

export const loginUser = async (req, res) => {
  // Implement login logic
};
```

### Adding MongoDB Models

**1. Create model file in `server/models/`:**

```javascript
// server/models/User.js
import mongoose from "mongoose";

const userSchema = new mongoose.Schema({
  name: String,
  email: { type: String, unique: true },
  password: String,
  createdAt: { type: Date, default: Date.now }
});

export default mongoose.model("User", userSchema);
```

---

## 🔐 Security Best Practices

- ✅ Never commit `.env` files
- ✅ Use strong JWT secrets (minimum 32 characters)
- ✅ Hash passwords with bcrypt
- ✅ Validate user input on backend
- ✅ Use HTTPS in production
- ✅ Rotate credentials regularly
- ✅ Enable MongoDB IP whitelisting
- ✅ Use environment variables for all secrets

---

## 📚 Useful Resources

- **Express.js Docs:** https://expressjs.com/
- **MongoDB Docs:** https://docs.mongodb.com/
- **Mongoose Docs:** https://mongoosejs.com/
- **React Docs:** https://react.dev/
- **Material-UI Docs:** https://mui.com/
- **JWT.io:** https://jwt.io/

---

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

---

## 📄 License

This project is licensed under the ISC License - see the LICENSE file for details.

---

## 📧 Support

For issues and questions:
- Create an issue in the GitHub repository
- Check existing documentation
- Review the troubleshooting section above

---

## 🚀 Deployment Guide

### Backend Deployment (Heroku/Railway/Render)

1. Set environment variables in hosting platform
2. Push to git
3. Platform automatically deploys

### Frontend Deployment (Vercel/Netlify)

1. Update API base URL for production
2. Build: `npm run build`
3. Deploy the `build/` folder

---

**Last Updated:** September 10, 2026  
**Version:** 1.0.0  
**Status:** In Development 🔨
