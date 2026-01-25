# Git Checklist – Thao tác chi tiết từng bước

**Dành cho:** Tất cả thành viên khi làm việc với Git & GitHub.

---

## 🎯 Nguyên tắc cốt lõi

```
Một người = Một branch = Một nhiệm vụ
```

- ✅ Code & Git commands: làm trên máy local (Terminal/VS Code)
- ✅ Review & merge: làm trên GitHub Web
- ❌ Không push trực tiếp lên `main` / `develop`
- ❌ Không force push
- ❌ Không commit code chưa chạy

---

## ⚙️ ONE-TIME SETUP (Lần đầu)

### Bước 1: Clone repository

```bash
git clone <repo-url>
cd <project-name>
```

### Bước 2: Chuyển sang develop

```bash
git checkout develop
git pull
```

✅ Xong setup!

---

## 📅 MỖI NGÀY TRƯỚC KHI BẮT ĐẦU CODE

### Bước 1: Kiểm tra nhánh hiện tại

```bash
git branch
```

✅ Phải thấy `* develop` (hoặc tên nhánh khác nếu đang làm feature)

### Bước 2: Cập nhật code mới nhất từ develop

```bash
git checkout develop
git pull origin develop
```

### Bước 3: Tạo nhánh feature mới

```bash
git checkout -b feature/<tên-chức-năng>
```

**Ví dụ:**

```bash
git checkout -b feature/login-page
git checkout -b feature/user-profile
git checkout -b feature/api-authentication
```

✅ Bây giờ bạn có thể bắt đầu code!

---

## 💻 TRONG QUÁ TRÌNH LÀMVỊỆC

### Bước 1: Code & kiểm tra

- Viết code
- Test trên máy local
- **Không commit code chưa chạy**

### Bước 2: Commit nhỏ, đúng mục đích

```bash
git add .
git commit -m "feat: mô tả ngắn gọn"
```

**Quy tắc commit message:**

- `feat: ` – thêm chức năng mới
- `fix: ` – sửa lỗi
- `ui: ` – thay đổi giao diện
- `refactor: ` – tối ưu code
- `docs: ` – cập nhật tài liệu

**Ví dụ:**

```bash
git commit -m "feat: add user login API"
git commit -m "fix: resolve password validation error"
git commit -m "ui: update dashboard layout"
```

### Bước 3: Push branch lên GitHub

```bash
git push -u origin feature/<tên-nhánh>
```

✅ Nhánh của bạn đã lên GitHub!

---

## 🔀 TẠO PULL REQUEST (GitHub Web)

### Trên GitHub Web:

1. Vào **Pull Requests** tab
2. Click **New Pull Request**
3. **Base:** `develop` ← **Compare:** `feature/<tên>`
4. Điền thông tin:
   - **Title:** Tóm tắt chức năng
   - **Description:**

     ```markdown
     ## 📝 Mô tả

     Chức năng được thêm / sửa lỗi.

     ## 🔍 Kiểm tra

     - [x] Chạy test thành công
     - [x] Không có console error
     - [x] Kiểm tra tính năng

     ## 📸 Screenshot (nếu UI)

     (Attachment hình ảnh)
     ```
5. Chọn **Reviewers** (ít nhất 1-2 người)
6. Click **Create Pull Request**

✅ PR của bạn sẵn sàng review!

---

## 🔧 KHI PR BỊ YÊU CẦU CHỈNH SỬA

### Trên máy local:

```bash
# Kiểm tra đúng branch
git branch

# Sửa code theo review comment
# ... (sửa files)

# Commit thêm
git add .
git commit -m "fix: update theo review"
git push
```

### Trên GitHub:

- PR tự động cập nhật commit mới
- **Không tạo PR mới**
- Reviewer sẽ xem lại

✅ Lặp lại cho đến khi approve!

---

## ✅ SAU KHI MERGE THÀNH CÔNG

### Bước 1: Dọn dẹp branch trên máy

```bash
git branch -d feature/<tên>
```

### Bước 2: Xóa branch trên GitHub (nếu chưa auto-delete)

```bash
git push origin --delete feature/<tên>
```

### Bước 3: Cập nhật develop trên máy

```bash
git checkout develop
git pull origin develop
```

✅ Sẵn sàng làm feature tiếp theo!

---

## ⛔ NHỮNG VIỆC TUYỆT ĐỐI KHÔNG ĐƯỢC LÀM

| ❌ Không làm                               | ✅ Thay vào đó                |
| ------------------------------------------ | ----------------------------- |
| Push trực tiếp vào `main` / `develop`      | Tạo feature branch & PR       |
| Force push (`git push --force`)            | Liên hệ reviewer nếu cần undo |
| Commit code chưa chạy / chưa test          | Test trên local trước commit  |
| Làm nhiều chức năng trong 1 branch         | 1 branch = 1 chức năng        |
| Commit file bị ignore (node_modules, .env) | Kiểm tra `.gitignore`         |
| Sửa code người khác mà không trao đổi      | Trao đổi trước qua chat/PR    |

---

## 🚨 GỨP LẠI NHANH

### Setup lần đầu:

```bash
git clone <url>
cd <project>
git checkout develop
```

### Trước khi bắt đầu mỗi ngày:

```bash
git checkout develop
git pull
git checkout -b feature/<tên>
```

### Trong quá trình làm việc:

```bash
git add .
git commit -m "type: description"
git push -u origin feature/<tên>
```

### Tạo PR trên GitHub Web → Review → Merge

### Sau khi merge:

```bash
git branch -d feature/<tên>
git checkout develop
git pull
```

---

## 📚 Tài liệu liên quan

- **Quy tắc & Code Style:** [CONTRIBUTING.md](CONTRIBUTING.md)
- **Hướng dẫn cài đặt:** [INSTALL.md](INSTALL.md)
- **Tổng quan dự án:** [README.md](README.md)

## ⚠️ CHÚ Ý: KHÔNG merge local trước PR

**❌ Sai (KHÔNG NÊN):**
```bash
# Code ở feature branch
git checkout develop
git merge feature/login-page  # ⚠️ Merge local

# Sau đó push feature
git checkout feature/login-page
git push origin feature/login-page
```

**✅ Đúng (NÊN):**
```bash
# Code ở feature branch
# Test code (không merge develop)
npm start

# Push feature lên GitHub
git push -u origin feature/login-page

# Tạo PR trên GitHub để merge
# GitHub sẽ tự động merge nếu không conflict
```

**Lý do:** Nếu PR bị reject, bạn không cần revert `develop` local.
