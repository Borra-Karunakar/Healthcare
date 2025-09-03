# Healthcare & Wellness Management System - Backend

This is the **backend service** of the Healthcare & Wellness Management System built with **Spring Boot 3**, **Spring Security (JWT)**, **Spring Data JPA**, and **MySQL**.

---

## 🚀 Features
- User authentication & authorization with **JWT**
- Role-based access: **Admin**, **Provider**, **Patient**
- Manage patients, providers, and appointments
- Wellness services management
- Payments & enrollments modules
- REST API with **Swagger documentation**
- MySQL database integration

---

## 🛠️ Tech Stack
- **Java 17**
- **Spring Boot 3**
- **Spring Security (JWT)**
- **Spring Data JPA / Hibernate**
- **MySQL**
- **Swagger (springdoc-openapi)**

---

## ⚙️ Setup & Installation

### 1️⃣ Clone the Repository


git clone https://github.com/Borra-Karunakar/healthcare-backend.git 

''' ###


2️⃣ Configure Database

Update src/main/resources/application.properties with your MySQL details:

server.port=8081

spring.datasource.url=jdbc:mysql://localhost:3306/healthcare_db?useSSL=false&allowPublicKeyRetrieval=true
spring.datasource.username=your_mysql_user
spring.datasource.password=your_mysql_password

spring.jpa.hibernate.ddl-auto=update
spring.jpa.show-sql=true
spring.jpa.properties.hibernate.dialect=org.hibernate.dialect.MySQLDialect

app.jwt.secret=ChangeThisSuperSecretKey!ChangeThisSuperSecretKey!
app.jwt.expiration-ms=86400000

3️⃣ Run the Application
mvn spring-boot:run

📖 API Documentation

Once the backend is running, you can access the API docs:

Swagger UI → http://localhost:8081/swagger-ui.html

OpenAPI JSON → http://localhost:8081/api-docs

🔑 Default Roles & Sample Users

When the app runs, bootstrap data inserts default users:

Admin

Email: admin@example.com

Password: Admin@123

Role: ADMIN

Provider

Email: sneha.kapoor@example.com

Password: Provider@123

Role: PROVIDER

Patient (can be registered via API or frontend)

📂 Project Structure
src/main/java/com/example/healthcare
│── controller/     # REST controllers (Admin, Auth, Patient, Provider, etc.)
│── entities/       # JPA entities (User, Patient, Provider, Appointment, etc.)
│── repository/     # Spring Data repositories
│── service/        # Business logic
│── security/       # JWT filters, token utils, security config
│── config/         # Swagger + Security configs
│── HealthcareApplication.java

📌 Sample API Endpoints
🔐 Authentication
# Login
POST http://localhost:8081/api/auth/login
Content-Type: application/json

{
  "email": "admin@example.com",
  "password": "Admin@123"
}


Response:

{
  "token": "jwt_token_here",
  "role": "ADMIN"
}

👤 Register Patient
POST http://localhost:8081/api/auth/register/patient
Content-Type: application/json

{
  "name": "Kanni",
  "email": "karunakarks81@gmail.com",
  "password": "Patient@123",
  "phone": "9876543210"
}

📅 Book Appointment
POST http://localhost:8081/api/appointments
Authorization: Bearer <jwt_token>
Content-Type: application/json

{
  "patientId": 1,
  "providerId": 2,
  "appointmentTime": "2025-09-05T11:30:00",
  "notes": "General checkup"
}

🧘 Wellness Services
GET http://localhost:8081/api/services
Authorization: Bearer <jwt_token>

🏥 Admin - View All Providers
GET http://localhost:8081/api/admin/providers
Authorization: Bearer <jwt_token>

✅ Next Steps

Integrate with frontend (React + Bootstrap UI)

Add payment gateways

Deploy on Docker / AWS

👨‍💻 Author

Borra Karunakar
📧 karunakarsk17@gmail.com


---

⚡ This README is **backend-only** and fully aligned with your Spring Boot project.  
