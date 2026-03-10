# ShopEx — Complete E-Commerce Platform

A fully functional, production-ready e-commerce system with a premium storefront and a powerful admin dashboard. **No server required** — runs entirely in the browser using localStorage for data persistence.

---

## 🚀 Quick Start

1. Open `index.html` in any modern browser — that's it!
2. For admin: open `admin/index.html`

**Demo Credentials:**
| Role     | Email                | Password  |
|----------|----------------------|-----------|
| Admin    | admin@shopex.com     | admin123  |
| Customer | jane@example.com     | jane123   |

---

## 📁 Project Structure

```
shop/
├── index.html              ← Main storefront (single-page app)
├── css/
│   └── main.css            ← Store styles (luxury editorial theme)
├── js/
│   ├── database.js         ← Data layer (localStorage CRUD)
│   └── app.js              ← Store app controller & page logic
├── admin/
│   ├── index.html          ← Admin dashboard (single-page app)
│   ├── css/
│   │   └── admin.css       ← Admin dashboard styles
│   └── js/
│       └── admin.js        ← Admin controllers & section logic
└── images/
    └── products/           ← Place local product images here
```

---

## 🛍️ Store Features

### Homepage
- Full-screen hero with animated background
- Shop-by-category grid (dynamically generated from DB)
- Featured products grid (filterable)
- Promotional banner with coupon code
- Trust strip (shipping, returns, security)
- Newsletter signup

### Shop / Product Listing
- Filter sidebar: categories, price range, search
- Sort by: featured, price (asc/desc), rating, newest
- Product count display
- Real-time filtering (no page reload)

### Product Detail
- Image gallery with thumbnail switcher
- Star rating display
- Quantity selector
- "Add to Cart" and "Wishlist" actions
- Related products
- Stock status, shipping & return info

### Shopping Cart
- Slide-out cart sidebar
- Add/remove/update quantities
- Subtotal + shipping calculation
- "Free shipping over $100" logic

### Checkout
- Contact information form
- Shipping address form
- Payment method selection (Card, PayPal, Apple Pay)
- Live order summary
- Order placement → success screen

### Authentication
- Customer registration
- Login/logout with session persistence
- "My Account" page with order history
- Admin role detection (redirects to admin)

### Search
- Full-text search across product names and descriptions
- Results page with count

---

## ⚡ Admin Dashboard Features

### Dashboard Overview
- Revenue, Orders, Products, Customers stats
- Monthly sales bar chart (last 6 months)
- Order status breakdown
- Recent orders table
- Top products by reviews

### Products Management
- Table with image, name, category, price, stock, rating
- Search and filter by category
- **Add Product** — full modal with:
  - Name, category, price, original price (for discount %)
  - Stock quantity, badge label (New/Sale/Best Seller)
  - Rating, review count
  - Description
  - Featured toggle (appears on homepage)
  - Image URLs (one per line, with live preview)
- **Edit Product** — pre-filled modal
- **Delete Product** — with confirmation

### Categories Management
- List all categories with icon, slug, description, product count
- Add/Edit/Delete categories
- Auto-generates slug from name

### Orders Management
- Full order list with customer, items, total, status
- **Status update** — inline dropdown (pending → processing → shipped → delivered → cancelled)
- **View Details** — modal with full order breakdown (items, address, payment)
- Search by customer name or order ID
- Filter by status
- Delete orders

### Users Management
- All users with role, order count, total spent, join date
- **Add User** — name, email, password, role
- **Edit User** — update any field
- **Delete User** (non-admin users only)
- Search by name or email

### Settings
- Store name, email, currency, tax rate
- Notification toggles
- Data export/reset options
- Admin account management

---

## 🗄️ Database Schema (localStorage)

### Products
```json
{
  "id": 1,
  "name": "Pro Wireless Headphones",
  "category_id": 1,
  "price": 299.99,
  "original_price": 399.99,
  "stock": 45,
  "rating": 4.8,
  "reviews": 234,
  "description": "...",
  "images": ["url1", "url2"],
  "featured": true,
  "badge": "Best Seller",
  "created_at": "2025-01-01T00:00:00Z"
}
```

### Categories
```json
{ "id": 1, "name": "Electronics", "slug": "electronics", "icon": "⚡", "description": "...", "color": "#6366f1" }
```

### Users
```json
{ "id": 1, "name": "Admin User", "email": "admin@shopex.com", "password": "admin123", "role": "admin", "created_at": "..." }
```

### Orders
```json
{
  "id": 1,
  "user_id": 2,
  "user_name": "Jane Cooper",
  "items": [{ "product_id": 1, "name": "...", "price": 299.99, "qty": 1, "image": "..." }],
  "total": 488.99,
  "status": "delivered",
  "payment": "card",
  "address": { "street": "123 Main St", "city": "New York", "zip": "10001", "country": "US" },
  "created_at": "2025-01-15T10:30:00Z"
}
```

---

## 🎨 Design System

### Store
- **Fonts**: Playfair Display (headings) + DM Sans (body)
- **Theme**: Luxury editorial — warm paper tones, gold accent (#c8a96e), dark ink
- **Aesthetic**: Refined minimalism with editorial flair

### Admin
- **Font**: Plus Jakarta Sans
- **Theme**: Clean modern — light grey background, white cards, indigo primary
- **Aesthetic**: Professional SaaS dashboard

---

## 🔧 How to Add Real Products

1. Open `admin/index.html`
2. Go to **Products → Add Product**
3. Paste Unsplash image URLs (free high-quality): `https://images.unsplash.com/photo-XXXXXXX?w=600&q=80`
4. Fill in all details and click **Save Product**
5. Products appear immediately on the store

---

## 🌐 Deploying to a Server

This project is pure HTML/CSS/JS — deploy anywhere:

**GitHub Pages:**
1. Push the `shop/` folder to a GitHub repo
2. Enable GitHub Pages on the `main` branch

**Netlify:**
1. Drag the `shop/` folder to app.netlify.com/drop

**Any Web Host:**
1. Upload all files maintaining the directory structure
2. Access via `index.html`

> **Note:** localStorage data is per-browser. For a real multi-user production app, replace `js/database.js` with API calls to a backend (Node.js/Express + MongoDB, or any REST API).

---

## 📦 Seeded Demo Data

- **12 products** across 6 categories with real Unsplash images
- **6 categories**: Electronics, Clothing, Home & Living, Sports, Books, Beauty
- **3 users**: 1 admin, 2 customers
- **4 orders** in various statuses (pending, processing, shipped, delivered)
