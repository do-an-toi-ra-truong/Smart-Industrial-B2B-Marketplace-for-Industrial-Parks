# Smart Industrial B2B Marketplace for Industrial Parks

## 1. Project Overview
This project builds a **B2B e-commerce platform** connecting enterprises within industrial parks.
It enables businesses to publish products/services, send RFQs, compare suppliers, and manage transactions digitally.

The system also supports **industrial park administrators** with centralized data for **Smart City** development.

---

## 2. Objectives
- Digitize B2B transactions in industrial parks
- Reduce manual supplier discovery and quotation processes
- Improve transparency and efficiency in B2B commerce
- Provide data for Smart Economy & Smart Governance

---

## 3. Target Users
- Enterprises in industrial parks
- Material, equipment, and service suppliers
- Industrial park administrators

---

## 4. Technology Stack

### Frontend
- React + TypeScript
- RESTful API

### Backend
- Java Spring Boot
- Spring Data JPA
- MySQL

### Tools & Workflow
- GitHub
- Git Flow (main / develop / feature)
- VS Code / IntelliJ IDEA
- Postman

---

## 5. Project Structure (High-level)

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

## 6. Getting Started

- 📦 **Installation & Run Guide**  
  See [INSTALL.md](./INSTALL.md)

- 🤝 **Contribution Guidelines**  
  See [CONTRIBUTING.md](./CONTRIBUTING.md)

- ✅ **Daily Git Workflow Checklist**  
  See [GitChecklist.md](./GitChecklist.md)

---

## 7. Team

- Nguyễn Phước Ân Điển – Frontend / Backend
- Dương Tấn Phát – Frontend / Backend
- Vũ Quang Huy – Frontend / Backend

Instructor: Ung Văn Giàu (Project Supervisor)

---

## 8. Notes
- Do not commit `node_modules`, `target`, `.env`
- All major changes must go through Pull Request
