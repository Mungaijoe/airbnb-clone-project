# Airbnb Clone Project

## Overview
This project is a full-stack web application inspired by Airbnb.

## Project Goals
- Recreate the core features of Airbnb
- Learn full-stack web development
- Practice responsive design and RESTful APIs


## Team Roles

### 1. Backend Developer
Responsible for building the server-side logic, APIs, and integrating with the database. Ensures business logic is enforced and routes are secure and performant.

### 2. Frontend Developer
Creates the user interface using modern frameworks and libraries. Ensures responsiveness, interactivity, and integration with backend APIs.

### 3. Database Administrator (DBA)
Designs and manages the database structure, ensures data integrity, backups, and performance tuning.

### 4. UI/UX Designer
Focuses on the design and user experience of the application, including layouts, color schemes, and user flows.

### 5. DevOps Engineer
Handles deployment, CI/CD pipelines, monitoring, and infrastructure. Ensures reliability and scalability.

### 6. QA Tester
Tests the application manually and/or through automation to ensure functionality, security, and performance are up to standard.

---

## Technology Stack

- **React.js**: Frontend library used to build dynamic and responsive user interfaces.
- **Tailwind CSS**: Utility-first CSS framework to quickly design custom UI components.
- **Node.js**: JavaScript runtime used for building fast and scalable backend services.
- **Express.js**: Web framework for Node.js to handle routes and RESTful API endpoints.
- **MongoDB**: NoSQL database to store user, property, booking, and payment data.
- **JWT (JSON Web Tokens)**: Used for securing authentication and authorization mechanisms.
- **Render/Heroku**: Services used to deploy and manage the backend server.

---

## Database Design

### 1. Users
- `id`: Unique identifier
- `name`: Full name
- `email`: Email address
- `password`: Hashed password
- `role`: Guest or Host

### 2. Properties
- `id`: Unique property ID
- `title`: Property title
- `location`: Address and city
- `price`: Cost per night
- `owner_id`: Linked to the User

### 3. Bookings
- `id`: Booking ID
- `user_id`: Linked to the User
- `property_id`: Linked to the Property
- `start_date`: Start of the booking
- `end_date`: End of the booking

### 4. Reviews
- `id`: Review ID
- `user_id`: Reviewer
- `property_id`: Reviewed property
- `rating`: Numeric rating
- `comment`: Review text

### 5. Payments
- `id`: Payment ID
- `booking_id`: Related booking
- `amount`: Payment amount
- `payment_date`: When the payment was made
- `status`: Paid or pending

### Entity Relationships
- A **User** can own many **Properties**
- A **Property** can have many **Bookings**
- A **Booking** belongs to one **User** and one **Property**
- A **Property** can have many **Reviews**
- A **Payment** is linked to one **Booking**

---

## Feature Breakdown

### 1. User Management
Allows users to sign up, log in, and manage profiles. Ensures user data is securely stored and accessible.

### 2. Property Management
Hosts can add, update, or delete property listings. Includes form-based entry and image uploads.

### 3. Booking System
Users can view property availability, make bookings, and receive confirmations.

### 4. Payment Integration
Secure payment system for processing bookings using third-party services.

### 5. Review System
Users can leave ratings and comments for properties they’ve booked.

---

## API Security

### Authentication
Only authenticated users can perform certain actions (like bookings, property management). Implemented using JWT.

### Authorization
Role-based access control ensures that only hosts can manage listings and only guests can make bookings.

### Rate Limiting
Prevents abuse of APIs by limiting the number of requests from a single IP.

### Input Validation & Sanitization
Protects against injection attacks by validating all input data.

### Why Security is Crucial:
- Protects user data (PII)
- Prevents unauthorized access
- Ensures safe financial transactions
- Builds trust with users

---

## CI/CD Pipeline

### What is CI/CD?
CI/CD (Continuous Integration and Continuous Deployment) automates testing and deployment of code. It ensures updates are frequent, reliable, and tested.

### Tools Used:
- **GitHub Actions**: For testing and deploying code on push or PR
- **Docker**: For containerizing the app across environments
- **Vercel**: Auto-deploy frontend changes
- **Heroku/Render**: Deploy backend with auto-redeploy from GitHub

---