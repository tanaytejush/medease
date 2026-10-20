# MedEase

A full-stack **doctor appointment booking system**. Patients browse doctors and book appointments, doctors manage their schedule, and admins manage the doctors and all bookings.

## Features

**Patients** (`frontend`)
- Sign up, log in and manage a profile
- Browse doctors and view availability
- Book, view and pay for appointments (Razorpay and Stripe)

**Doctors** (`admin` panel, doctor login)
- Dashboard with appointment overview
- View and manage their appointments
- Edit their profile

**Admin** (`admin` panel, admin login)
- Dashboard with platform stats
- Add doctors and manage the doctor list
- View all appointments

## Tech stack

| Layer | Technology |
|-------|------------|
| Frontend and admin | React, Vite, React Router, Axios, React Toastify |
| Backend | Node.js, Express |
| Database | MongoDB with Mongoose |
| Auth | JWT, bcrypt (separate middleware for user, doctor and admin) |
| Uploads | Multer and Cloudinary |
| Payments | Razorpay, Stripe |

## Project structure

```
medease/
  frontend/   Patient-facing React app
  admin/      Admin and doctor React dashboard
  backend/    Express API (routes, controllers, models, middleware)
```

API routes are mounted at `/api/user`, `/api/admin` and `/api/doctor`.

## Getting started

### Prerequisites
- Node.js 18+
- A MongoDB database (local or Atlas)
- Cloudinary account (for doctor images)
- Razorpay and/or Stripe keys (for payments)

### 1. Backend

```bash
cd backend
npm install
```

Create `backend/.env`:

```env
PORT=4000
MONGODB_URI=your_mongodb_connection_string
JWT_SECRET=your_jwt_secret
ADMIN_EMAIL=admin@example.com
ADMIN_PASSWORD=choose_a_strong_password
CURRENCY=INR
CLOUDINARY_NAME=your_cloud_name
CLOUDINARY_API_KEY=your_api_key
CLOUDINARY_SECRET_KEY=your_api_secret
RAZORPAY_KEY_ID=your_key_id
RAZORPAY_KEY_SECRET=your_key_secret
STRIPE_SECRET_KEY=your_stripe_secret
```

`ADMIN_EMAIL` and `ADMIN_PASSWORD` are the credentials for the admin login. Then start the server:

```bash
npm run server
```

### 2. Frontend and admin

Create a `.env` file in both `frontend/` and `admin/`:

```env
VITE_BACKEND_URL=http://localhost:4000
VITE_CURRENCY=₹
VITE_RAZORPAY_KEY_ID=your_key_id
```

Then run each app in its own terminal:

```bash
cd frontend && npm install && npm run dev
cd admin && npm install && npm run dev
```

## Security note

Never commit `.env` files or real keys. Keep all secrets in environment variables.


---

<sub>Made by [tanaytejush](https://github.com/tanaytejush)</sub>
