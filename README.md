# 🏨 StayEase - Hotel Booking System 
https://github.com/user-attachments/assets/6748bef8-d791-4b2d-99fa-ac3488b0c1b1

A full-featured Hotel Management System built with Spring Boot & React that supports:

- Role-based access control
- Hotel & room management
- Booking & reservation system
- Payment integration
- Admin dashboard analytics

---

## 🚀 Features
👥 Role-Based Access Control
| Role | Capabilities |
|------|--------------|
| **Admin**	| Manage hotels • View all bookings • System oversight |
| **Hotel** | Manager	Manage rooms • View bookings • Update availability |
| **User**	| Browse hotels • Book rooms • View booking history |

---

### 🏨 Hotel & Room Management
- Create and manage hotels with detailed information
- Add rooms with amenities and pricing
- Real-time availability tracking
- Search and filter hotels by location, price, amenities

---

### 📅 Booking System
- Secure room booking with date validation
- Prevent double booking conflicts
- Booking confirmation and status tracking
- Cancellation and modification support

---

### 💳 Payment Integration
- Razorpay payment gateway integration
- Secure payment processing
- Payment status tracking

---

### 🔐 Security & Authentication
- JWT-based secure authentication
- Password hashing using BCrypt
- Role-based API access restrictions
- CORS enabled for frontend integration

---

## 🛠 Tech Stack

### 🧩 Backend

| Component | Technology |
| ---------------- | --------------------- |
| Framework | **Spring Boot 3.5.6** |
| Security | **Spring Security 6.5.5 + JWT** |
| Database | **MySQL + Spring Data JPA** |
| API Docs | **Swagger / OpenAPI 3.1** |
| Testing | **JUnit 5, Mockito** |
| Build Tool | **Maven** |

---

### ⚡ Frontend

| Component        | Technology            |
| ---------------- | --------------------- |
| Framework        | **React 18**          |
| Routing          | **React Router DOM**  |
| HTTP Client      | **Axios**             |
| Styling          | **Tailwind CSS**      |
| State Management | **React Context API** |

---

### ☁️ Cloud Services

| Service             | Provider                |
| ------------------- | ----------------------- |
| Backend Deployment  | **Render**              |
| Frontend Deployment | **Netlify**             |
| Database            | **PostgreSQL (Render)** |

---

## 📋 API Endpoints
### 🔑 Authentication Endpoints
| Method | Endpoint | Description | Access |
|--------|----------------------|------------------------|---------------|
| Method | Endpoint             | Description            | Access        |
| POST   | `/api/auth/signup`   | User Registration      | **Public**    |
| POST   | `/api/auth/login`    | Login & Token Issuance | **Public**    |
| POST   | `/api/auth/validate` | Validate JWT Token     | **All Roles** |

---

### 🏨 Hotel Endpoints

| Method | Endpoint             | Description      | Access     |
| ------ | -------------------- | ---------------- | ---------- |
| GET    | `/api/hotels`        | Get all hotels   | **Public** |
| GET    | `/api/hotels/{id}`   | Get hotel by ID  | **Public** |
| GET    | `/api/hotels/search` | Search hotels    | **Public** |
| POST   | `/api/hotels`        | Create new hotel | **Admin**  |
| PUT    | `/api/hotels/{id}`   | Update hotel     | **Admin**  |
| DELETE | `/api/hotels/{id}`   | Delete hotel     | **Admin**  |

---
### 🛏 Room Endpoints
| Method | Endpoint                     | Description        | Access     |
| ------ | ---------------------------- | ------------------ | ---------- |
| GET    | `/api/rooms/hotel/{hotelId}` | Get rooms by hotel | **Public** |
| GET    | `/api/rooms/{id}`            | Get room by ID     | **Public** |
| POST   | `/api/rooms`                 | Create new room    | **Admin**  |
| PUT    | `/api/rooms/{id}`            | Update room        | **Admin**  |
| DELETE | `/api/rooms/{id}`            | Delete room        | **Admin**  |

---
### 📅 Booking Endpoints
| Method | Endpoint                    | Description        | Access         |
| ------ | --------------------------- | ------------------ | -------------- |
| POST   | `/api/bookings`             | Create new booking | **User**       |
| GET    | `/api/bookings/user`        | Get user bookings  | **User**       |
| GET    | `/api/bookings/{id}`        | Get booking by ID  | **User/Admin** |
| PUT    | `/api/bookings/{id}/cancel` | Cancel booking     | **User**       |
| GET    | `/api/bookings`             | Get all bookings   | **Admin**      |

---

### 💳 Payment Endpoints
| Method | Endpoint                            | Description            | Access   |
| ------ | ----------------------------------- | ---------------------- | -------- |
| POST   | `/api/payments/create-order`        | Create payment order   | **User** |
| POST   | `/api/payments/verify`              | Verify payment         | **User** |
| GET    | `/api/payments/booking/{bookingId}` | Get payment by booking | **User** |

---

### 🔍 Search Endpoints
| Method | Endpoint                   | Description               | Access     |
| ------ | -------------------------- | ------------------------- | ---------- |
| GET    | `/api/search/hotels`       | Search hotels by criteria | **Public** |
| GET    | `/api/search/availability` | Check room availability   | **Public** |

---


<details> <summary><strong>📁 stayease.backend</strong></summary>
</details><details> <summary><strong>📁 stayease.frontend</strong>

</summary>

</details>

---

## 🧪 Testing

### Unit Test Coverage

| Test Class             | Focus Area                                  |
| ---------------------- | ------------------------------------------- |
| **AuthServiceTest**    | User registration & authentication flows    |
| **HotelServiceTest**   | Hotel CRUD operations & management          |
| **BookingServiceTest** | Booking creation, validation & cancellation |
| **PaymentServiceTest** | Payment processing & verification           |

### 🚀 Run Tests
```
./mvnw test
```

---

## 🗄 Database Schema
### 📊 Key Entities Overview
| Entity       | Important Fields                                   |
| ------------ | -------------------------------------------------- |
| **Users**    | id, username, email, password, role                |
| **Hotels**   | id, name, description, location, amenities, images |
| **Rooms**    | id, hotel_id, type, price, amenities, availability |
| **Bookings** | id, user_id, room_id, check_in, check_out, status  |
| **Payments** | id, booking_id, amount, status, razorpay_order_id  |

---

### ⚙️ Installation & Setup

Prerequisites
- Java 17+
- MySQL 14+
- Maven 3.6+
- Node.js 18+

---

## Local Development Setup

### 1️⃣ Clone Repository

```bash
git clone <your-repo-url>
cd stayease.backend
```
---

### 2️⃣ Create Database in MySQL
```sql
CREATE DATABASE stayease_db;
```

---

### 3️⃣ Update application.properties
```app.properties
spring.datasource.url=jdbc:postgresql://localhost:5432/stayease_db
spring.datasource.username=your_username
spring.datasource.password=your_password
```

---

### 4️⃣ Run the Backend Application

```
./mvnw spring-boot:run
```
### 5️⃣ Run the Frontend Application
```
cd stayease.frontend
npm install
npm run dev
```

---

### 6️⃣ Access the Application

| Service                  | URL                                                                                        |
| ------------------------ | ------------------------------------------------------------------------------------------ |
| **Frontend Application** | [http://localhost:5173](http://localhost:5173)                                             |
| **Backend API**          | [http://localhost:8080](http://localhost:8080)                                             |
| **Swagger UI**           | [http://localhost:8080/swagger-ui/index.html](http://localhost:8080/swagger-ui/index.html) |
| **OpenAPI JSON Spec**    | [http://localhost:8080/v3/api-docs](http://localhost:8080/v3/api-docs)                     |

---

## 🚀 Deployment
- Backend (Render)
- Connect GitHub repository
- Set environment variables
- Auto-deploy on push

## Frontend (Netlify)
- Deploy frontend build
- Set API Base URL: https://stayease-klft.onrender.com/api

---

## 🔐 Required Environment Variables
```
# Database
JDBC_DATABASE_URL=your_database_url
SPRING_DATASOURCE_USERNAME=your_username
SPRING_DATASOURCE_PASSWORD=your_password

# JWT
JWT_SECRET=your_jwt_secret

# Razorpay
RAZORPAY_KEY_ID=your_razorpay_key
RAZORPAY_KEY_SECRET=your_razorpay_secret

# Server
PORT=8080
```
## 📚 API Documentation
| Resource         | URL                      |
| ---------------- | ------------------------ |
| **Swagger UI**   | `/swagger-ui/index.html` |
| **OpenAPI Spec** | `/v3/api-docs`           |

---

## 👥 Default Users (Auto-Created on First Run)

| Role          | Email                                           | Password |
| ------------- | ----------------------------------------------- | -------- |
| **Admin**     | [admin@stayease.com](mailto:admin@stayease.com) | admin123 |
| **User**      | [user@stayease.com](mailto:user@stayease.com)   | user123  |
| **Demo User** | [demo@stayease.com](mailto:demo@stayease.com)   | demo123  |

---

<h1>👨‍💻 Author</h1>
<h2><b>Rachit Sharma</b></h2>
<h3>rachitsharma300</h3>




