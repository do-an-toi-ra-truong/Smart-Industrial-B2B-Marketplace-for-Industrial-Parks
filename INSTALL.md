# INSTALLATION GUIDE

Hướng dẫn cài đặt môi trường và chạy dự án **Smart Industrial B2B Marketplace for Industrial Parks** trên máy cá nhân.

---

## 📋 Yêu cầu hệ thống

### Phần mềm bắt buộc

- **Node.js** >= v24
- **Java JDK** >= 17
- **MySQL** >= 8.0
- **Maven**
- **Git**

### Công cụ khuyến nghị

- **Visual Studio Code** (Frontend development)
- **IntelliJ IDEA** (Backend development)
- **Postman** (API testing)

---

## 🔄 Clone repository

```bash
git clone https://github.com/username/repository-name.git
cd repository-name
git checkout develop
```

---

## 🔧 Cài đặt Backend (Spring Boot)

### Bước 1: Di chuyển vào thư mục Backend

```bash
cd Back_End/sping_e_commerce/ecommerce-api
```

### Bước 2: Cấu hình Database

Mở file `src/main/resources/application.properties` hoặc `application.yml`:

```properties
spring.datasource.url=jdbc:mysql://localhost:3306/b2b_ecommerce
spring.datasource.username=root
spring.datasource.password=your_password
spring.datasource.driver-class-name=com.mysql.cj.jdbc.Driver
spring.jpa.hibernate.ddl-auto=update
```

**Lưu ý:**

- Tạo database `b2b_ecommerce` trong MySQL trước
- ⚠️ Không commit file này nếu chứa mật khẩu thực

### Bước 3: Chạy Backend

```bash
mvn clean install
mvn spring-boot:run
```

✅ Backend sẽ chạy tại: **http://localhost:8080**

---

## 💻 Cài đặt Frontend (React)

### Bước 1: Di chuyển vào thư mục Frontend

```bash
cd Front_End/Front_End_Admin_seller/AdminLTE-4.0.0-rc4
```

### Bước 2: Cài đặt Dependencies

```bash
npm install
```

### Bước 3: Chạy Frontend

```bash
npm start
```

✅ Frontend sẽ chạy tại: **http://localhost:3000**

---

## ✅ Kiểm tra hệ thống

- [ ] Truy cập **http://localhost:3000** – Frontend tải bình thường
- [ ] Truy cập **http://localhost:8080** – Backend API phản hồi
- [ ] Dùng **Postman** gọi API test (vd: `GET /api/users`)
- [ ] Kiểm tra kết nối frontend ↔ backend trong browser console

---

## 🐛 Troubleshooting

### Frontend không tải

```bash
# Xóa node_modules và cài lại
rm -rf node_modules package-lock.json
npm install
npm start
```

### Backend lỗi kết nối Database

- Kiểm tra MySQL đang chạy: `mysql -u root -p`
- Kiểm tra `application.properties`: username, password, database name
- Tạo database: `CREATE DATABASE b2b_ecommerce;`

### Port 3000 / 8080 đang bị sử dụng

```bash
# Đổi port trong .env hoặc config
# Frontend: thêm PORT=3001 trước npm start
# Backend: chỉnh server.port=8081 trong application.properties
```

---

## ⚠️ Ghi chú quan trọng

- ❌ Không push: `node_modules/`, `target/`, `.env`, mật khẩu database
- 📝 Luôn pull code mới nhất trước khi làm việc: `git pull origin develop`
- 🔐 Bảo mật: Không share mật khẩu database, không commit credentials

---

## 📞 Cần giúp?

- Tạo **GitHub Issue** để báo lỗi cụ thể
- Liên hệ trưởng nhóm nếu gặp vấn đề môi trường
- Xem [CONTRIBUTING.md](CONTRIBUTING.md) để hiểu quy tắc làm việc
