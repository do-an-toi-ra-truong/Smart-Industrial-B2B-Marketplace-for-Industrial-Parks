# INSTALLATION GUIDE

## 1. Mục đích
Tài liệu này hướng dẫn cài đặt môi trường và chạy dự án **Smart Industrial B2B Marketplace for Industrial Parks** trên máy cá nhân dành cho các thành viên trong nhóm phát triển.

---

## 2. Yêu cầu hệ thống

### 2.1. Phần mềm cần cài đặt
- Node.js phiên bản 18 trở lên  
- Java Development Kit (JDK) phiên bản 17 trở lên  
- MySQL phiên bản 8.0 trở lên  
- Maven  
- Git  

### 2.2. Công cụ khuyến nghị
- Visual Studio Code (Frontend)  
- IntelliJ IDEA (Backend)  
- Postman (Test API)  

---

## 3. Clone source code từ GitHub

Clone repository về máy (bash):  
git clone https://github.com/username/repository-name.git  

Di chuyển vào thư mục project (bash):  
cd repository-name  

Chuyển sang nhánh develop để làm việc (bash):  
git checkout develop  

---

## 4. Cài đặt và chạy Backend (Spring Boot)

Di chuyển vào thư mục backend (bash):  
cd backend  

### 4.1. Cấu hình cơ sở dữ liệu
Mở file application.properties hoặc application.yml và cấu hình:

spring.datasource.url=jdbc:mysql://localhost:3306/b2b_ecommerce  
spring.datasource.username=root  
spring.datasource.password=your_password  

Lưu ý:  
- Database b2b_ecommerce cần được tạo trước trong MySQL  
- Không commit file cấu hình chứa mật khẩu lên GitHub  

### 4.2. Chạy backend
Chạy Spring Boot application (bash):  
mvn spring-boot:run  

Sau khi chạy thành công, backend hoạt động tại:  
http://localhost:8080  

---

## 5. Cài đặt và chạy Frontend (React)

Quay lại thư mục gốc và vào frontend (bash):  
cd frontend  

Cài đặt các thư viện cần thiết (bash):  
npm install  

Chạy ứng dụng frontend (bash):  
npm start  

Frontend chạy tại:  
http://localhost:3000  

---

## 6. Kiểm tra hệ thống
- Truy cập frontend tại trình duyệt  
- Gọi thử API bằng Postman  
- Kiểm tra kết nối frontend ↔ backend  

---

## 7. Lưu ý quan trọng
- Không push thư mục node_modules và target lên GitHub  
- Không chia sẻ file .env hoặc mật khẩu database  
- Luôn pull code mới nhất từ nhánh develop trước khi làm việc  

---

## 8. Hỗ trợ
Nếu gặp lỗi trong quá trình cài đặt, vui lòng liên hệ trưởng nhóm hoặc tạo issue trên GitHub repository.
