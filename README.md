# Smart Industrial B2B Marketplace for Industrial Parks

## 📌 Giới thiệu dự án

Dự án xây dựng **nền tảng thương mại điện tử B2B** kết nối các doanh nghiệp trong khu công nghiệp (KCN). Cho phép doanh nghiệp:

- Đăng tải sản phẩm/dịch vụ
- Tìm kiếm nhà cung cấp
- Gửi yêu cầu báo giá (RFQ)
- Đặt hàng trực tuyến

Hệ thống hướng đến **tự động hóa – minh bạch hóa quy trình giao dịch** và hỗ trợ **ban quản lý KCN** trong quản lý thông tin doanh nghiệp phục vụ phát triển **Smart City**.

---

## 🎯 Mục tiêu

- ✅ Xây dựng sàn B2B dùng chung cho các doanh nghiệp trong KCN
- ✅ Giảm thời gian tìm kiếm nhà cung cấp và báo giá thủ công
- ✅ Minh bạch hóa và số hóa quy trình giao dịch B2B
- ✅ Cung cấp dữ liệu phục vụ Smart Economy & Smart Governance

---

## 👥 Đối tượng sử dụng

- **Doanh nghiệp** trong khu công nghiệp
- **Nhà cung cấp** nguyên vật liệu, thiết bị, dịch vụ
- **Ban quản lý KCN** (Admin)

---

## 🛠️ Công nghệ sử dụng

### Frontend

- React + TypeScript
- RESTful API
- UI Template (AdminLTE 4.0)

### Backend

- Java Spring Boot
- Spring Data JPA
- RESTful API
- MySQL

### DevOps & Tools

- GitHub (quản lý source code)
- Git Flow (main / develop / feature)
- VS Code / IntelliJ IDEA
- Postman (API testing)

---

## 📖 Table of Contents

| Phần                                   | Mục đích                                   | Đối tượng                 |
| -------------------------------------- | ------------------------------------------ | ------------------------- |
| **[INSTALL.md](INSTALL.md)**           | Hướng dẫn cài đặt & chạy dự án             | Thành viên mới, developer |
| **[CONTRIBUTING.md](CONTRIBUTING.md)** | Quy tắc làm việc, code style, commit rules | Tất cả thành viên         |
| **[GitChecklist.md](GitChecklist.md)** | Checklist thao tác Git từng bước           | Tất cả thành viên         |

---

## 📂 Cấu trúc thư mục

```
project-root/
├── Back_End/
│   └── sping_e_commerce/
│       └── ecommerce-api/          # Java Spring Boot API
│           ├── src/
│           ├── pom.xml
│           └── mvnw
│
├── Front_End/
│   ├── Front_End_Admin_seller/     # Admin Dashboard (AdminLTE)
│   │   └── AdminLTE-4.0.0-rc4/
│   └── Front_End_Buyer/            # Buyer UI
│       └── index.html
│
├── README.md                        # (File này)
├── INSTALL.md                       # Hướng dẫn cài đặt
├── CONTRIBUTING.md                  # Quy tắc làm việc
├── GitChecklist.md                  # Checklist Git
└── .gitignore
```

---

## 👨‍💻 Thành viên nhóm

| Tên                          | Vai trò            |
| ---------------------------- | ------------------ |
| Nguyễn Phước Ân Điển         | Frontend / Backend |
| Dương Tấn Phát               | Frontend / Backend |
| Vũ Quang Huy                 | Frontend / Backend |
| **Giảng viên:** Ung Văn Giàu | Project Manager    |

---

## 🚀 Quick Start

### Dành cho thành viên mới:

1. Đọc file **[INSTALL.md](INSTALL.md)** để cài đặt môi trường
2. Đọc file **[CONTRIBUTING.md](CONTRIBUTING.md)** để hiểu quy tắc làm việc
3. Dùng **[GitChecklist.md](GitChecklist.md)** như một checklist khi làm việc với Git

### Chạy dự án:

```bash
# Backend
cd Back_End/sping_e_commerce/ecommerce-api
mvn spring-boot:run          # http://localhost:8080

# Frontend
cd Front_End/Front_End_Admin_seller/AdminLTE-4.0.0-rc4
npm install
npm start                     # http://localhost:3000
```

Xem chi tiết tại **[INSTALL.md](INSTALL.md)**.

---

## ⚠️ Ghi chú quan trọng

- ❌ **Không push** lên GitHub: `node_modules/`, `target/`, `.env`, mật khẩu database
- 📋 **Luôn pull code** mới nhất từ `develop` trước khi bắt đầu làm việc
- 🔀 **Không code trực tiếp** trên `main` hoặc `develop` – tạo feature branch
- 📝 **Mọi thay đổi** lớn cần thông qua Pull Request (PR)

Xem thêm: [Git Workflow Overview](CONTRIBUTING.md#3-git-workflow-sử-dụng-trong-dự-án)

---

## 📞 Hỗ trợ & Báo lỗi

- Sử dụng **GitHub Issues** để báo lỗi hoặc đề xuất cải tiến
- Liên hệ trưởng nhóm nếu gặp vấn đề trong quá trình cài đặt
- Mô tả rõ vấn đề và cách tái hiện lỗi
