# Installation Guide

## 1. Purpose
This document guides developers to **set up and run the project locally**.
It focuses strictly on environment setup and execution.

---

## 2. System Requirements

### 2.1 Required Software
- Node.js >= 18
- Java JDK >= 17
- MySQL >= 8.0
- Maven
- Git

### 2.2 Recommended Tools
- Visual Studio Code (Frontend)
- IntelliJ IDEA (Backend)
- Postman (API Testing)

---

## 3. Clone Repository

Clone the source code from GitHub:

git clone <repository-url>

Move into project directory:

cd <repository-name>

Switch to develop branch:

git checkout develop

---

## 4. Backend Setup (Spring Boot)

Move to backend directory:

cd backend

### 4.1 Database Configuration
Edit `application.properties` or `application.yml`:

spring.datasource.url=jdbc:mysql://localhost:3306/b2b_ecommerce  
spring.datasource.username=root  
spring.datasource.password=your_password  

Notes:
- Database `b2b_ecommerce` must exist before running.
- Do not commit files containing credentials.

### 4.2 Run Backend
Start Spring Boot application:

mvn spring-boot:run

Backend will be available at:

http://localhost:8080

---

## 5. Frontend Setup (React)

Move to frontend directory:

cd frontend

Install dependencies:

npm install

Run frontend application:

npm start

Frontend will be available at:

http://localhost:3000

---

## 6. System Verification
- Access frontend via browser
- Call APIs using Postman
- Verify frontend-backend connectivity

---

## 7. Important Notes
- Do not commit `node_modules`, `target`, `.env`
- Always pull latest code from `develop` before working
- For Git workflow and contribution rules, see CONTRIBUTING.md
