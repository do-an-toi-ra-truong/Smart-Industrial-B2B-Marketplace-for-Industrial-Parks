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

---

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

---

## 📦 GIT STASH - Cất giữ tạm thời thay đổi

### Khi nào dùng Stash:

- Đang code, cần switch branch gấp
- Quên pull develop mới trước khi code
- Code sai, muốn quay lại
- Có nhiều thay đổi, muốn lưu tạm

### Stash message chuẩn:

**Format:** `<type>: <description> - <status>`

**Ví dụ:**

```bash
git stash push -m "feat: login form - WIP"
git stash push -m "fix: API validation - paused"
git stash push -m "ui: dashboard - need review"
```

### Các lệnh cơ bản:

```bash
# Cất giữ thay đổi (với message)
git stash push -m "feat: login - WIP"

# Xem danh sách stash
git stash list

# Lấy lại (xóa stash)
git stash pop

# Lấy lại nhưng giữ stash
git stash apply stash@{0}

# Xóa stash
git stash drop stash@{0}
```

---

## 🎯 Scenario thực tế - Người mới hay mắc phải

### **Scenario 1: Cần switch branch gấp (đang code chưa xong)**

**Tình huống:**

- Bạn đang code `feature/login-page`
- Trưởng nhóm yêu cầu switch sang `feature/reset-password` để fix bug gấp
- Code login chưa xong, không muốn commit chưa test

**Cách sai (❌ KHÔNG NÊN):**

```bash
# Bạn cố tằng switch branch mà không save code
git checkout feature/reset-password
# Error: Your local changes to the following files would be overwritten...
# ❌ Git ngăn bạn, không cho switch
```

**Cách đúng (✅ NÊN):**

```bash
# 1. Cất giữ code login chưa hoàn thành
git stash push -m "feat: login form validation - WIP"

# 2. Kiểm tra đã cất giữ
git stash list
# Output: stash@{0}: feat: login form validation - WIP

# 3. Switch sang branch reset-password
git checkout feature/reset-password

# 4. Code, commit, push
git add .
git commit -m "fix: reset password email validation"
git push origin feature/reset-password

# 5. Quay lại feature/login
git checkout feature/login-page

# 6. Lấy code login cũ
git stash pop

# 7. Tiếp tục code login...
git add .
git commit -m "feat: complete login form"
git push origin feature/login-page
```

---

### **Scenario 2: Quên pull develop mới, code bị conflict**

**Tình huống:**

- Bạn tạo `feature/user-profile` từ develop
- Code được vài hôm
- Phát hiện develop GitHub có update từ thành viên khác
- Phải pull develop mới, nhưng bạn vẫn đang code chưa commit

**Cách sai (❌ KHÔNG NÊN):**

```bash
# Cố pull mà không save code
git checkout develop
git pull origin develop
# Sẽ bị conflict hoặc mất code
```

**Cách đúng (✅ NÊN):**

```bash
# 1. Cất giữ code chưa hoàn thành
git stash push -m "feat: user profile form - WIP"

# 2. Switch sang develop
git checkout develop

# 3. Pull develop mới từ GitHub
git pull origin develop
# ✅ Develop local đã cập nhật

# 4. Quay lại feature branch
git checkout feature/user-profile

# 5. Lấy code cũ từ stash
git stash pop

# 6. Nếu có conflict, sửa
# (Git sẽ báo conflict trong files)
# - Sửa conflict trong code
# - git add .
# - git commit -m "merge: resolve develop conflicts"

# 7. Tiếp tục code
```

**Nếu pop có conflict (Lỗi phổ biến):**

```bash
# Bạn sẽ thấy conflict markers trong file
# <<<<<<< Updated upstream
# develop code
# =======
# your stash code
# >>>>>>> Stashed changes

# ✅ Cách xử lý:
# 1. Mở file, chọn code nào là đúng (giữ cả 2 hoặc một phần)
git add .
git commit -m "merge: resolve stash conflicts"

# 2. Hoặc abort và thử lại
git merge --abort
git stash drop  # Xóa stash, quay lại
```

---

### **Scenario 3: Code sai, muốn hủy và quay lại**

**Tình huống:**

- Bạn code validation form được 2 giờ
- Phát hiện logic hoàn toàn sai
- Muốn quay lại code trước đó
- Nhưng không chắc chắn 100%, nên muốn giữ code cũ tạm

**Cách sai (❌ KHÔNG NÊN):**

```bash
# Reset trực tiếp (mất code luôn)
git reset --hard HEAD
# ❌ Tất cả thay đổi bị xóa vĩnh viễn
```

**Cách đúng (✅ NÊN):**

```bash
# 1. Cất giữ code sai trước (phòng cần)
git stash push -m "fix: validation logic - WRONG, need revert"

# 2. Reset về trạng thái trước
git reset --hard HEAD

# 3. Test lại code cũ
npm start
# ✅ Code cũ hoạt động bình thường

# 4. Nếu cần, có thể lấy code sai ra sửa
git stash list
# stash@{0}: fix: validation logic - WRONG, need revert

# 5. Lấy stash để xem hoặc sửa
git stash apply stash@{0}

# 6. Sửa code...
# Nếu code xong
git add .
git commit -m "fix: correct validation logic"

# 7. Hoặc bỏ đi
git reset --hard HEAD
git stash drop stash@{0}
```

---

### **Scenario 4: Có quá nhiều file thay đổi, muốn stash chọn lọc**

**Tình huống:**

- Bạn sửa 5 files, nhưng chỉ muốn stash 3 files
- 2 files còn lại muốn commit riêng

**Cách sai (❌ KHÔNG NÊN):**

```bash
# Stash hết, rồi pop lại toàn bộ
git stash push -m "multiple changes"
# Khó kiểm soát, dễ lộn
```

**Cách đúng (✅ NÊN):**

```bash
# 1. Add chỉ những file muốn commit trước
git add file1.js file2.js
git commit -m "feat: update feature 1"
git push

# 2. Stash những file còn lại
git stash push -m "feat: update feature 2 - WIP"

# 3. Hoặc sử dụng stash specific files
git stash push src/components/Form.tsx src/utils/validate.ts -m "feat: form validation - WIP"
```

---

### **Scenario 5: Stash lâu, quên stash là cái gì (❌ Phổ biến)**

**Tình huống:**

- Bạn stash 1 tuần trước
- Bây giờ quên stash đó là cái gì, có nên lấy không

**Cách sai (❌ KHÔNG NÊN):**

```bash
# Pop stash mà không xem nội dung
git stash pop
# Dù sao rồi sẽ xung đột hoặc ghi đè code
```

**Cách đúng (✅ NÊN):**

```bash
# 1. Xem danh sách stash
git stash list
# Output:
# stash@{0}: feat: login form - WIP
# stash@{1}: fix: password validation - paused
# stash@{2}: ui: dashboard - need review

# 2. Xem chi tiết stash cụ thể
git stash show -p stash@{1}
# ✅ Hiện tất cả thay đổi, chọn có lấy không

# 3. Nếu không cần, xóa
git stash drop stash@{1}

# 4. Nếu cần, lấy
git stash pop stash@{1}

# 5. Hoặc apply (lấy nhưng giữ stash)
git stash apply stash@{1}
```

---

### **Scenario 6: Stash conflict sau khi pull develop mới (⚠️ Khó)**

**Tình huống:**

- Feature branch code cũ
- Develop GitHub có update lớn từ người khác
- Pull develop, rồi pop stash → bị conflict
- Không biết cách xử lý

**Cách sai (❌ KHÔNG NÊN):**

```bash
# Bỏ stash, reset develop
git stash drop
git reset --hard origin/develop
# ❌ Mất code
```

**Cách đúng (✅ NÊN):**

```bash
# 1. Cất giữ (nếu chưa)
git stash push -m "feat: user profile - WIP"

# 2. Switch develop, pull mới
git checkout develop
git pull origin develop

# 3. Quay lại feature
git checkout feature/user-profile

# 4. Pop stash (có conflict)
git stash pop
# Conflict in src/api/user.ts
# Conflict in src/components/UserCard.tsx

# 5. Xem conflict
git status
# modified: src/api/user.ts (conflict)
# modified: src/components/UserCard.tsx (conflict)

# 6. Sửa conflict trong VS Code
# - Mở file conflict
# - Chọn "Accept Incoming" / "Accept Current" / "Accept Both"
# - Hoặc edit trực tiếp

# 7. Mark resolved
git add src/api/user.ts
git add src/components/UserCard.tsx

# 8. Commit merge
git commit -m "merge: resolve stash + develop conflicts"

# 9. Test code
npm start

# 10. Push
git push origin feature/user-profile
```

---

### ⚠️ Lưu ý quan trọng:

| Lưu ý                  | Giải thích                                  |
| ---------------------- | ------------------------------------------- |
| **Stash chỉ local**    | Không push lên GitHub, chỉ tồn tại máy bạn  |
| **Stash có hạn**       | Nếu xóa máy/reset repo, stash mất           |
| **Đừng stash quá lâu** | > 1 tuần → commit thay vì stash             |
| **Luôn test sau pop**  | Conflict có thể xảy ra, test kỹ             |
| **Commit > Stash**     | Khi code xong → commit, không stash lâu dài |
| **Message chuẩn**      | Giúp bạn nhớ stash là cái gì                |

---

## 📝 Flowchart - Khi nào dùng Stash?

```
Đang code
    ↓
Cần switch branch / pull / quay lại?
    ├─ YES → git stash push -m "..."
    │         Switch / Pull / Reset
    │         git stash pop
    │
    └─ NO → Tiếp tục code
             git add .
             git commit -m "..."
             git push
```
