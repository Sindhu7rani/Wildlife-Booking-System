# Wildlife Tourism Booking System

A full-stack web application for wildlife tourism booking, built using **J2EE (Servlets, JSP, JDBC)** and **MySQL**, with a responsive front-end using **HTML/CSS**. Users can browse and book safaris, stays, packages, and guides. Admins can manage all tours, bookings, and users.

---

## Table of Contents
- [Features](#features)
- [Technologies Used](#technologies-used)
- [Database Design](#database-design)
- [Project Structure](#project-structure)
- [Setup Instructions](#setup-instructions)
- [Usage](#usage)
- [Screenshots](#screenshots)
- [Author](#author)

---

## Features

### User Features
- User signup, login, forgot password, and profile update
- Browse and view Safaris, Stays, Packages, and Guides
- Book a tour with date validation and automatic price calculation
- View, update, or cancel bookings

### Admin Features
- Manage Safaris, Stays, Packages, and Guides (Add, Update, Delete)
- Manage bookings: change status (Booked, Confirmed, Cancelled)
- Manage users

### Additional Features
- Session management for login/logout
- Input validation for forms
- MVC architecture for clean code separation
- DAO pattern for database operations
- POJO classes representing all entities

---

## Technologies Used
- **Backend:** Java (Servlets, JSP), JDBC, DAO/DTO Pattern
- **Frontend:** HTML5, CSS3, JSP
- **Database:** MySQL
- **Architecture:** MVC
- **Tools:** Eclipse, VS Code, Git/GitHub, Maven

---

## Database Design

### Tables
- **user** → user information (user_id, name, email, phone, password, address)
- **booking** → booking details (booking_id, user_id, item_type, item_name, dates, price, status)
- **safari** → safari tours information
- **stay** → accommodation information
- **packages** → tour packages
- **guides** → tour guides

### Relationships
- `booking.user_id` → foreign key referencing `user.user_id`
- Each booking references an item (Safari, Stay, Package, Guide) via `item_type` and `item_name`

---

## Project Structure

com.wild_tour
│
├─ connection
│ └─ Connector.java
│
├─ dao
│ ├─ UserDAO.java / UserDAOImpl.java
│ ├─ BookingDAO.java / BookingDAOImpl.java
│ ├─ GuideDAO.java / GuideDAOImpl.java
│ ├─ PackagesDAO.java / PackagesDAOImpl.java
│ ├─ SafariDAO.java / SafariDAOImpl.java
│ └─ StayDAO.java / StayDAOImpl.java
│
├─ dto
│ ├─ User.java
│ ├─ Booking.java
│ ├─ Guide.java
│ ├─ Packages.java
│ ├─ Safari.java
│ └─ Stay.java
│
├─ servlet
│ ├─ Signup.java
│ ├─ Login.java
│ ├─ ForgotPassword.java
│ ├─ Update.java
│ ├─ Bookings.java
│ ├─ CancelBooking.java
│ ├─ UpdateBookingStatus.java
│ ├─ GuideAction.java
│ ├─ PackagesAction.java
│ ├─ SafariAction.java
│ └─ StayAction.java
│
└─ webapp (JSP / HTML / CSS files)


---

## Setup Instructions

1. Clone the repository:
```bash
git clone https://github.com/Sindhu7rani/Wildlife-Tourism-Booking-System.git


Open the project in Eclipse or VS Code.

Create a MySQL database:

CREATE DATABASE wildlife;


Create tables as per the SQL scripts in /database folder (or create manually).

Update database connection in Connector.java if required:

String url = "jdbc:mysql://localhost:3306/wildlife";
String user = "root";
String password = "tiger";


Deploy project on Tomcat server (or any servlet container).

Open in browser: http://localhost:8080/WildlifeTourism/

Usage

User can signup → login → browse tours → book a safari/stay/package/guide → manage bookings

Admin can login → manage tours, bookings, and users
