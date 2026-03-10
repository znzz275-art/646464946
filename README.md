# 🛍️ ShopLux — Full-Stack E-Commerce Platform

A production-ready e-commerce platform with a full admin dashboard, built with React, Node.js, Express, and MongoDB.

## ✨ Features

### Customer Store
- Beautiful, responsive homepage with featured products
- Product listing with search & pagination
- Product details with image gallery
- Star ratings & customer reviews
- Shopping cart (add, remove, update quantity)
- Checkout with order confirmation
- User registration & login (JWT auth)
- User profile & order history

### Admin Dashboard (`/admin`)
- Overview: total users, products, orders, revenue
- Product management: add, edit, delete, image upload
- Order management: view, update status, order details
- User management: view & delete users
- Fully protected with admin role

## 🚀 Getting Started

### Prerequisites
- Node.js v18+
- MongoDB (local or Atlas)

### Installation

```bash
# 1. Clone the repo
git clone https://github.com/yourusername/ecommerce-project.git
cd ecommerce-project

# 2. Set up environment variables
cp .env.example server/.env
# Edit server/.env with your MongoDB URI and JWT secret

# 3. Install all dependencies
npm run install-all

# 4. Seed the database (optional)
cd server && npm run seed

# 5. Start development servers
cd ..
npm run dev
```

- **Frontend**: http://localhost:5173
- **Backend API**: http://localhost:5000

### Default Admin Account (after seeding)
- Email: `admin@shoplux.com`
- Password: `admin123`

## 🏗️ Project Structure

```
ecommerce-project/
├── client/               # React frontend (Vite + Tailwind)
│   └── src/
│       ├── components/   # Reusable components
│       ├── pages/        # Route pages
│       ├── context/      # React Context (Auth, Cart)
│       ├── hooks/        # Custom hooks
│       └── utils/        # API helpers
├── server/               # Node.js + Express backend
│   ├── controllers/      # Route controllers
│   ├── models/           # Mongoose models
│   ├── routes/           # API routes
│   ├── middleware/        # Auth & error middleware
│   └── utils/            # Helpers & seeder
├── uploads/              # Uploaded product images
├── .env.example
└── package.json
```

## 🛠️ Tech Stack

| Layer | Technology |
|-------|-----------|
| Frontend | React 18, Vite, Tailwind CSS |
| Backend | Node.js, Express.js |
| Database | MongoDB, Mongoose |
| Auth | JWT (JSON Web Tokens) |
| Images | Multer (local storage) |
| State | React Context API |

## 📦 Build for Production

```bash
# Build frontend
npm run build

# Start production server
npm start
```
