# Food-Delivery 🍕

A full-stack, real-time Food Delivery application built using the MERN stack (MongoDB, Express, React, Node.js). This project includes distinct portals for **Customers**, **Restaurant Owners**, and **Delivery Partners** with real-time tracking, secure payments, and a robust geospatial search mechanism.

---

## 🚀 Key Features

### 👤 Role-Based Portals

#### 1. Customers (`user`)
* **Interactive Map & Search**: Browse nearby restaurants and items using geospatial queries (MongoDB `2dsphere` index).
* **Cart & Checkout**: Add food items to the cart, manage quantities, and proceed to checkout.
* **Secure Payments**: Integrated with **Razorpay** for handling order payments seamlessly.
* **Live Order Tracking**: Track the assigned delivery partner's location in real-time on a map powered by **Leaflet** and **Socket.io**.
* **Password Reset**: OTP-based authentication reset sent via email.

#### 2. Restaurant Owners (`owner`)
* **Shop Registration**: Register and manage shop profile, details, and geographical location.
* **Menu Management**: Perform full CRUD operations on food items (uploading item images using **Multer** and **Cloudinary**).
* **Order Management**: Receive customer orders in real-time, update preparation status, and monitor assignment.
* **Analytics Dashboard**: View and visualize shop sales and orders using interactive graphs powered by **Recharts**.

#### 3. Delivery Partners (`deliveryBoy`)
* **Delivery Dashboard**: View assigned order requests with customer details, restaurant locations, and delivery addresses.
* **Live Location Broadcasting**: Broadcast coordinates in real-time using Web Geolocation API and Socket.io to allow customers and owners to track delivery progress.
* **Order Status Controls**: Mark items as picked up or successfully delivered.

---

## 🛠️ Technology Stack

### Frontend
* **Core**: React 19, JavaScript (ES6+), HTML5, CSS3
* **Styling**: Tailwind CSS v4 for utility-first responsive styling
* **State Management**: Redux Toolkit & React-Redux
* **Routing**: React Router DOM (v7)
* **Real-time Sync**: Socket.io Client
* **Maps & Geo-location**: Leaflet & React-Leaflet
* **Charts**: Recharts
* **Authentication & Services**: Firebase Integration
* **Bundler**: Vite

### Backend
* **Runtime**: Node.js & Express
* **Database**: MongoDB with Mongoose (Geospatial querying with `2dsphere` index)
* **Real-time Engine**: Socket.io Server
* **Media Uploads**: Multer & Cloudinary SDK
* **Payment Gateway**: Razorpay Node SDK
* **Security & Auth**: JSON Web Tokens (JWT), bcryptjs
* **Email Service**: Nodemailer (OTP Dispatch)

---

## 📂 Project Structure

```
Food-Delivery/
├── backend/
│   ├── config/          # Database & third-party configuration
│   ├── controllers/     # Controller logic for auth, items, orders, etc.
│   ├── middlewares/     # Authentication & file upload middlewares
│   ├── models/          # Mongoose Schemas (User, Shop, Item, Order, DeliveryAssignment)
│   ├── routes/          # Express API route declarations
│   ├── utils/           # Utility functions (helpers, mail templates)
│   ├── index.js         # Entry point for backend Express & Socket.io server
│   └── package.json
│
└── frontend/
    ├── src/
    │   ├── components/  # Reusable UI components (Nav, Dashboards, Tracking)
    │   ├── pages/       # Page components (CheckOut, ForgotPassword, SignUp, etc.)
    │   ├── redux/       # Redux slices and store configuration
    │   ├── firebase.js  # Firebase initialization settings
    │   └── main.jsx     # Frontend entry point
    └── package.json
```

---

## ⚙️ Setup & Installation

### Prerequisites
* [Node.js](https://nodejs.org/) installed on your machine.
* [MongoDB](https://www.mongodb.com/) instance (local or Atlas cluster).
* Cloudinary, Razorpay, and Firebase accounts for API keys.

---

### Backend Configuration

1. Navigate to the backend directory:
   ```bash
   cd backend
   ```
2. Install the backend dependencies:
   ```bash
   npm install
   ```
3. Create a `.env` file in the `backend/` directory and configure the following variables:
   ```env
   PORT=5000
   MONGO_URI=your_mongodb_connection_string
   JWT_SECRET=your_jwt_secret_key
   CLOUDINARY_CLOUD_NAME=your_cloudinary_cloud_name
   CLOUDINARY_API_KEY=your_cloudinary_api_key
   CLOUDINARY_API_SECRET=your_cloudinary_api_secret
   SMTP_HOST=your_smtp_host
   SMTP_PORT=your_smtp_port
   SMTP_MAIL=your_sender_email
   SMTP_PASSWORD=your_email_app_password
   RAZORPAY_KEY_ID=your_razorpay_key_id
   RAZORPAY_KEY_SECRET=your_razorpay_key_secret
   ```
4. Start the backend development server:
   ```bash
   npm run dev
   ```

---

### Frontend Configuration

1. Navigate to the frontend directory:
   ```bash
   cd ../frontend
   ```
2. Install the frontend dependencies:
   ```bash
   npm install
   ```
3. Create a `.env` file in the `frontend/` directory and configure the following variables:
   ```env
   VITE_FIREBASE_APIKEY=your_firebase_api_key
   VITE_GEOAPIKEY=your_geo_location_api_key
   VITE_RAZORPAY_KEY_ID=your_razorpay_key_id
   ```
4. Start the frontend development server:
   ```bash
   npm run dev
   ```
5. Open your browser and navigate to the local URL (usually `http://localhost:5173`).

---

## 🤝 Contributing

Contributions, issues, and feature requests are welcome! Feel free to check the issues page or submit pull requests.