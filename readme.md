# 🛒 QuickKart — Full Stack E-Commerce Application

QuickKart is a full-stack **MERN e-commerce web application** that provides a complete online shopping experience. It includes secure authentication, product and category management, shopping cart functionality, address management, order processing, online payments, product search, and an admin dashboard.

## 🌐 Live Demo

🚀 **Live Website:**  
https://quick-kart-full-stack-hto6.vercel.app/

---

## ✨ Features

### 👤 User Features

- User registration and login
- JWT-based authentication
- Access Token & Refresh Token
- Email verification
- Forgot password with OTP verification
- Update user profile
- Upload profile avatar
- Browse products by category and subcategory
- Search products
- Product pagination
- Add products to cart
- Update product quantity
- Remove products from cart
- Address management
- Cash on Delivery
- Online payment using Stripe
- View order history
- Responsive user interface

### 🛠️ Admin Features

- Admin authorization
- Add, update and delete products
- Category management
- Subcategory management
- Upload product images
- Manage product information
- Product inventory management

---

## 🧑‍💻 Tech Stack

### Frontend

- React.js
- JavaScript
- Redux Toolkit
- React Router
- Axios
- Tailwind CSS
- Context API
- React Icons

### Backend

- Node.js
- Express.js
- MongoDB
- Mongoose
- JWT Authentication
- bcrypt
- Multer
- Nodemailer
- Cookie Parser
- CORS
- Helmet
- Morgan

### Third-Party Services

- **Cloudinary** — Image storage and management
- **Stripe** — Online payment processing
- **Vercel** — Application deployment

---

## 🏗️ Application Architecture

```text
                    QuickKart
                        │
                ┌───────┴───────┐
                │               │
             Frontend         Backend
              React        Node + Express
                │               │
        Redux / Context         │
                │               │
              Axios ───────► REST API
                                │
                         Authentication
                          JWT Middleware
                                │
                           Controllers
                                │
                            Mongoose
                                │
                            MongoDB
                         ┌──────┴──────┐
                         │             │
                    Cloudinary      Stripe
```

---

## 🔐 Authentication Flow

QuickKart uses JWT-based authentication with Access Tokens and Refresh Tokens.

```text
User Login
    ↓
Validate Credentials
    ↓
bcrypt Password Verification
    ↓
Generate Access Token
    ↓
Generate Refresh Token
    ↓
Authenticated API Request
    ↓
JWT Authentication Middleware
    ↓
Protected Route
```

Passwords are hashed using **bcrypt** before being stored in the database.

---

## 💳 Payment Flow

QuickKart supports both **Cash on Delivery** and **Stripe online payments**.

```text
User Cart
    ↓
Checkout
    ↓
Select Address
    ↓
Choose Payment Method
    ↓
Stripe Checkout / Cash on Delivery
    ↓
Create Order
    ↓
Store Order in MongoDB
    ↓
Order History
```

---

## 🖼️ Image Upload Flow

Product and user images are handled using Multer and Cloudinary.

```text
User/Admin selects image
          ↓
       FormData
          ↓
        Multer
          ↓
      Cloudinary
          ↓
     Image URL
          ↓
       MongoDB
```

---

## 📂 Project Structure

```text
QuickKart/
│
├── client/
│   ├── public/
│   └── src/
│       ├── assets/
│       ├── components/
│       ├── layouts/
│       ├── pages/
│       ├── provider/
│       ├── route/
│       ├── store/
│       └── utils/
│
├── server/
│   ├── config/
│   ├── controllers/
│   ├── middleware/
│   ├── models/
│   ├── routes/
│   └── utils/
│
└── README.md
```

---

## 🔌 Major API Modules

The backend REST API contains modules for:

```text
/api/user
/api/product
/api/category
/api/subcategory
/api/cart
/api/address
/api/order
/api/file
```

These APIs handle authentication, products, categories, shopping carts, addresses, orders, payments and image uploads.

---

## 🗄️ Database Models

The application uses multiple MongoDB collections including:

- User
- Product
- Category
- SubCategory
- Cart Product
- Address
- Order

Mongoose references and `populate()` are used to retrieve related documents where required.

---

## 🔎 Product Search & Pagination

QuickKart supports product searching using MongoDB text indexing.

```javascript
productSchema.index({
    name: "text",
    description: "text"
});
```

Pagination improves performance by loading products in smaller batches instead of retrieving the entire collection at once.

```text
skip = (page - 1) × limit
```

---

## ⚙️ Environment Variables

Create a `.env` file inside the backend/server directory.

Example:

```env
PORT=8080

MONGODB_URI=your_mongodb_connection_string

SECRET_KEY_ACCESS_TOKEN=your_access_token_secret
SECRET_KEY_REFRESH_TOKEN=your_refresh_token_secret

CLOUDINARY_CLOUD_NAME=your_cloudinary_name
CLOUDINARY_API_KEY=your_cloudinary_api_key
CLOUDINARY_API_SECRET_KEY=your_cloudinary_secret

STRIPE_SECRET_KEY=your_stripe_secret_key

FRONTEND_URL=http://localhost:5173
```

> Never commit your `.env` file or secret API keys to GitHub.

---

## 🚀 Installation & Setup

### 1. Clone the repository

```bash
git clone YOUR_GITHUB_REPOSITORY_URL
```

### 2. Enter the project

```bash
cd QuickKart
```

### 3. Install Backend Dependencies

```bash
cd server
npm install
```

### 4. Start Backend

```bash
npm run dev
```

### 5. Install Frontend Dependencies

Open another terminal:

```bash
cd client
npm install
```

### 6. Start Frontend

```bash
npm run dev
```

The application will now run locally.

---

## 🔒 Security

QuickKart implements several security practices:

- Password hashing with bcrypt
- JWT authentication
- Access and refresh tokens
- HTTP-only cookies
- Role-based authorization
- Helmet security headers
- CORS configuration
- Environment variables for sensitive credentials
- Protected backend routes

---

## 📈 Future Improvements

Future versions of QuickKart can include:

- Product reviews and ratings
- Wishlist functionality
- Advanced filtering and sorting
- Coupon and discount system
- Order tracking
- Admin analytics dashboard
- Recommendation system
- Improved payment webhook security
- Automated testing
- Better API validation
- Performance optimization

---

## 🎯 Project Objective

The main objective of QuickKart is to demonstrate the development of a real-world full-stack e-commerce system using the MERN stack.

The project focuses on:

- Building scalable REST APIs
- Secure authentication and authorization
- Global state management
- Database relationships
- Payment gateway integration
- Cloud-based image management
- Responsive frontend development
- Full-stack application deployment
