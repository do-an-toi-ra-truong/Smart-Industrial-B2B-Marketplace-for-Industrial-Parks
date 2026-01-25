# Smart Industrial B2B Marketplace for Industrial Parks

## 1. Giới thiệu dự án
Dự án xây dựng **nền tảng thương mại điện tử B2B** kết nối các doanh nghiệp trong khu công nghiệp (KCN), cho phép doanh nghiệp đăng tải sản phẩm/dịch vụ, tìm kiếm nhà cung cấp, gửi yêu cầu báo giá (RFQ) và đặt hàng trực tuyến.

Hệ thống hướng đến việc **tự động hóa – minh bạch hóa quy trình giao dịch**, đồng thời hỗ trợ **ban quản lý KCN** trong việc quản lý thông tin doanh nghiệp và tổng hợp dữ liệu phục vụ phát triển **Smart City**.

---

## 2. Mục tiêu
- Xây dựng sàn B2B dùng chung cho các doanh nghiệp trong KCN  
- Giảm thời gian tìm kiếm nhà cung cấp và báo giá thủ công  
- Minh bạch hóa và số hóa quy trình giao dịch B2B  
- Cung cấp dữ liệu phục vụ Smart Economy & Smart Governance  

---

## 3. Đối tượng sử dụng
- Doanh nghiệp trong khu công nghiệp  
- Nhà cung cấp nguyên vật liệu, thiết bị, dịch vụ  
- Ban quản lý khu công nghiệp (Admin)  

---

## 4. Công nghệ sử dụng

### Frontend
- React + TypeScript  
- RESTful API  
- UI Template (Admin Dashboard)  

### Backend
- Java Spring Boot  
- Spring Data JPA  
- RESTful API  
- MySQL  

### Công cụ & DevOps
- GitHub (quản lý source code)  
- Git Flow (main / develop / feature)  
- VS Code / IntelliJ IDEA  
- Postman  

---

## 5. Cấu trúc thư mục

project-root/  
├── frontend/ (React TypeScript)  
│   ├── src/  
│   ├── public/  
│   └── package.json  
│  
├── backend/ (Spring Boot)  
│   ├── src/main/java  
│   ├── src/main/resources  
│   └── pom.xml  
│  
├── .gitignore  
└── README.md  

---

## 6. Cách chạy dự án (Run Project)

### 6.1. Yêu cầu môi trường
- Node.js >= 18  
- Java JDK >= 17  
- MySQL >= 8.0  
- Maven  

---

### 6.2. Chạy Backend (Spring Boot)

Di chuyển vào thư mục backend (bash):  
cd backend  

Cấu hình database trong file `application.properties` hoặc `application.yml`:

spring.datasource.url=jdbc:mysql://localhost:3306/b2b_ecommerce  
spring.datasource.username=root  
spring.datasource.password=your_password  

Chạy project backend (bash):  
mvn spring-boot:run  

Backend chạy tại:  
http://localhost:8080  

---

### 6.3. Chạy Frontend (React)

Di chuyển vào thư mục frontend (bash):  
cd frontend  

Cài đặt thư viện (bash):  
npm install  

Chạy project frontend (bash):  
npm start  

Frontend chạy tại:  
http://localhost:3000  

---

## 7. Quy trình làm việc nhóm (Git Workflow)

- main: nhánh ổn định, dùng để demo / bảo vệ  
- develop: nhánh phát triển chính  
- feature/*: mỗi chức năng một nhánh  

### Luồng làm việc
1. Tạo branch từ develop  
2. Code → commit  
3. Push branch → tạo Pull Request  
4. Review → merge vào develop  
5. Merge develop → main khi chuẩn bị demo hoặc bảo vệ  

---

## 8. Quy ước commit message

Cấu trúc commit:  
type: mô tả ngắn  

Các type sử dụng:
- feat: thêm chức năng mới  
- fix: sửa lỗi  
- ui: cập nhật giao diện  
- refactor: tối ưu code  
- docs: cập nhật tài liệu  

Ví dụ:
- feat: implement user management module  
- ui: design admin dashboard layout  

---

## 9. Thành viên nhóm
- Nguyễn Phước Ân Điển – Frontend / Backend 
- Dương Tấn Phát – Frontend / Backend  
- Vũ Quang Huy – Frontend / Backend 

Giảng viên Ung Văn Giàu - Project Manager

---

## 10. Ghi chú
- Không push node_modules, target, .env lên GitHub  
- Tuân thủ Git workflow và team convention  
- Mọi thay đổi lớn cần thông qua Pull Request  

