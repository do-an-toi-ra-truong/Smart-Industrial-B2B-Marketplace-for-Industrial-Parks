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

### Bước 3: Lấy nhánh main về (nếu cần demo)

```bash
git pull origin main
```

✅ Xong setup!

---

## 📋 Chuẩn bị trước khi demo

Khi chuẩn bị demo hoặc bảo vệ đồ án, thực hiện các bước sau:

### Bước 1: Tạo PR từ develop vào main (Github)

1. Trên GitHub, vào tab **Pull Requests**
2. Click **New Pull Request**
3. Chọn:
   - **Base branch**: `main`
   - **Compare branch**: `develop`
4. Điền tiêu đề: `chore: merge develop to main for demo`
5. Click **Create Pull Request**

### Bước 2: Review & Merge (Github)

1. Assign reviewer (hoặc team lead)
2. Đợi approve
3. Click **Merge Pull Request**

### Bước 3: Update nhánh main trên máy cá nhân để demo (Local)

```bash
git checkout main
git pull origin main
```

✅ Nhánh `main` giờ đã sẵn sàng cho demo trên máy của bạn!

---

## 📅 MỖI NGÀY TRƯỚC KHI BẮT ĐẦU CODE (Local)

### Bước 1: Kiểm tra nhánh hiện tại

```bash
git branch
```

✅ Phải thấy `* develop` (hoặc tên nhánh khác nếu đang làm feature)

### Bước 2: Cập nhật code mới nhất từ develop (nếu quên thì Ctrl+F Scenario 2)

```bash
git checkout develop
git pull origin develop
```

### Bước 3: Tạo nhánh feature mới (nếu quên và lỡ commit lên develop thì Ctrl+F Lỗi 6)

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

## 💻 TRONG QUÁ TRÌNH LÀM VIỆC (Local)

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

## 🔀 TẠO PULL REQUEST (GitHub)

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

## 🚨 Tóm tắt

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

## ⚠️ CHÚ Ý: KHÔNG merge feature mới vào develop ở local, push fearture lên github rồi tạo PR để merge với origin/develop

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

## 📦 GIT STASH - Cất giữ tạm thời những thay đổi

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
WIP là Work In Progress

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

---

## ⚠️ Các lỗi Git thường gặp khi làm việc với branch được bảo vệ (Bài học thực tế)

Repository sử dụng **Git Flow** với **branch protection** trên `main` và `develop`. Thành viên **không được push trực tiếp** vào hai nhánh này, bắt buộc phải tạo `feature/*` → PR → Review → Merge.

### 🚨 Lỗi 1: "rejected... branch is under protection" khi push

**Tình huống:**

```bash
git push origin develop
# ERROR: [remote rejected] develop (protected branch hook declined)
```

**Nguyên nhân:**

- `develop` có branch protection bật
- Bạn cố push trực tiếp mà không qua PR

**Cách xử lý (✅ ĐÚNG):**

```bash
# ❌ KHÔNG push trực tiếp
git push origin develop

# ✅ ĐÚNG - Tạo feature branch
git checkout -b feature/your-feature
git add .
git commit -m "feat: your feature"
git push -u origin feature/your-feature

# Rồi tạo PR trên GitHub
# Base: develop ← Compare: feature/your-feature
```

---

### 🚨 Lỗi 2: VS Code "Publish Branch" báo lỗi "Pull first"

**Tình huống:**

- Bạn code trên `feature/login-page`
- Click **Publish Branch** trên VS Code
- Báo lỗi: `failed to push some refs to 'origin'`

**Nguyên nhân:**

- Remote branch `feature/login-page` đã tồn tại với commit khác
- Có thể người khác push trước, hoặc push từ máy khác
- Git yêu cầu pull trước để merge

**Cách xử lý (✅ ĐÚNG):**

```bash
# 1. Pull branch feature từ remote
git pull origin feature/login-page

# 2. Nếu có conflict, sửa trong VS Code
# - Chọn "Accept Incoming" hoặc "Accept Current"
# - git add .

# 3. Commit merge
git commit -m "merge: resolve remote conflicts"

# 4. Push lại
git push origin feature/login-page

# 5. Hoặc dùng VS Code Source Control → ... → Pull
```

**Cách tránh lỗi này:**

```bash
# Cấu hình default push strategy
git config --global push.default current

# Ý nghĩa:
# - Mỗi khi push, git tự động tạo tracking branch remote
# - Tránh nhầm lẫn push sai branch
```

---

### 🚨 Lỗi 3: "non-fast-forward" reject khi push

**Tình huống:**

```bash
git push origin feature/user-profile
# ERROR: failed to push some refs to 'origin'
# hint: Updates were rejected because the tip of your current branch is behind
# hint: its remote counterpart.
```

**Nguyên nhân:**

- Remote branch có commit mà local branch không có
- Thường do push từ máy/người khác trước

**Cách xử lý (✅ ĐÚNG):**

```bash
# Cách 1: Pull trước (an toàn nhất)
git pull origin feature/user-profile
git push origin feature/user-profile

# Cách 2: Fetch + Rebase (nếu muốn history sạch)
git fetch origin
git rebase origin/feature/user-profile
git push origin feature/user-profile
```

**⚠️ NGUY HIỂM - KHÔNG NÊN:**

```bash
# ❌ Force push (ngoại trừ owner / test lúc clone)
git push --force origin feature/user-profile
# → Có thể xóa commit của người khác!
```

---

### 🚨 Lỗi 4: VS Code dùng Git khác PowerShell (Windows-specific)

**Tình huống:**

- Terminal PowerShell chạy lệnh git OK
- VS Code Source Control báo lỗi ngược lại
- Hoặc VS Code không nhận git commands

**Nguyên nhân (Windows):**

- Windows có thể cài Git 2 chỗ:
  - `C:\Program Files\Git\bin\git.exe` (Git cho PowerShell)
  - `C:\Program Files\Git for Windows\cmd\git.exe` (Git khác)
- VS Code dùng Git binary khác PowerShell

**Cách xử lý (✅ ĐÚNG):**

```bash
# 1. Kiểm tra Git path
which git
# Output: C:\Program Files\Git\bin\git

# 2. Cấu hình VS Code dùng Git path này
# Mở VS Code Settings (Ctrl+,)
# Tìm: "git.path"
# Nhập: "C:\Program Files\Git\bin\git.exe"

# 3. Reload VS Code (Ctrl+Shift+P → Reload Window)
```

**Nếu vẫn lỗi:**

```bash
# Cài đặt lại Git for Windows
# Tải từ: https://git-scm.com/download/win
# Hoặc dùng Chocolatey: choco install git
```

---

### 🚨 Lỗi 5: Push feature/* thành công nhưng PR vẫn không cho merge

**Tình huống:**

- Push `feature/payment` lên GitHub thành công
- Tạo PR: develop ← feature/payment
- GitHub báo: **"This branch cannot be merged"**

**Nguyên nhân:**

- Branch có conflict với develop
- Hoặc branch chưa pass CI/CD checks
- Hoặc yêu cầu reviewer chưa approve

**Cách xử lý (✅ ĐÚNG):**

```bash
# 1. Kiểm tra conflict
# GitHub sẽ báo "This branch has conflicts that must be resolved"

# 2. Resolve conflict ở local
git checkout feature/payment
git pull origin develop
# → Sẽ báo conflict nếu có

# 3. Sửa conflict trong file
# - Mở file, edit conflict markers
# git add .
# git commit -m "merge: resolve develop conflicts"
# git push origin feature/payment

# 4. Kiểm tra CI/CD checks
# - GitHub Actions sẽ chạy lại
# - Đợi tất cả test pass (xanh)

# 5. Yêu cầu reviewer
# - Thêm comment: @reviewer "Ready for review"
# - Hoặc assign lại reviewer nếu cần
```

---

### ✅ Checklist: Chuẩn bị Push Feature Branch

**Trước khi push:**

- [ ] Bạn đang ở branch `feature/*` (check: `git branch`)
- [ ] Code đã test trên local, không có lỗi
- [ ] Commit message tuân thủ format: `type: description`
- [ ] Không commit file bị ignore (`.env`, `node_modules/`)

**Khi push:**

```bash
# Bước 1: Kiểm tra branch
git branch
# Output: * feature/your-feature

# Bước 2: Pull develop mới nhất
git checkout develop
git pull origin develop

# Bước 3: Quay lại feature, merge develop (nếu cần)
git checkout feature/your-feature
git pull origin develop  # Pull develop vào feature
# Nếu conflict, sửa + add + commit

# Bước 4: Push feature
git push -u origin feature/your-feature
```

**Sau khi push:**

- [ ] GitHub sẽ hiện "Compare & pull request" → Click
- [ ] Chọn base: `develop`, compare: `feature/your-feature`
- [ ] Điền title + description rõ ràng
- [ ] Assign 1-2 reviewers
- [ ] Đợi CI/CD checks pass (xanh)
- [ ] Đợi reviewer approve

---

### ⚠️ Khi nào được phép Force Push?

**Chỉ được phép khi:**

- ✅ Branch `feature/*` chỉ của bạn (chưa ai else push)
- ✅ Branch chưa có PR được merge
- ✅ Bạn là owner repository

**Lệnh force push:**

```bash
# ⚠️ NGUY HIỂM - Xóa commit remote
git push --force origin feature/your-feature

# ✅ AN TOÀN HƠN - Chỉ push nếu local ahead
git push --force-with-lease origin feature/your-feature
```

**Cách tránh cần force push:**

```bash
# Thay vì reset, tạo branch mới sạch
git checkout -b feature/your-feature-v2
git cherry-pick commit-hash-1
git cherry-pick commit-hash-2
git push -u origin feature/your-feature-v2

# Xóa branch cũ
git branch -D feature/your-feature
git push origin --delete feature/your-feature
```

---

### 🎯 Flowchart: Cách xử lý khi push bị reject

```
git push origin feature/branch
      ↓
Có error?
    ├─ "protected branch" → ✅ Đúng, tạo PR qua GitHub
    ├─ "non-fast-forward" → ✅ git pull + git push
    ├─ "Pull first" → ✅ git pull origin feature/branch
    ├─ "force push needed" → ⚠️ Chi hỏi trưởng nhóm trước
    │
    └─ Thành công → GitHub sẽ báo "Compare & pull request"
                     → Tạo PR để merge vào develop
```

---

## 🚨 Lỗi 6: Code lộn vào develop và lỡ commit (❌ Phổ biến nhất)

**Tình huống:**

- Bạn quên tạo feature branch
- Code trực tiếp trên `develop`
- Đã commit: `git commit -m "feat: login page"`
- Chưa push lên GitHub

**Nguyên nhân:**

- Quên bước tạo `feature/*` branch
- Hoặc switch nhầm branch, rồi code mất tiêu chí

**Cách xử lý**

```bash
# Bước 1: Kiểm tra đang ở develop
git branch
# Output: * develop

# Bước 2: Xem commit vừa làm
git log --oneline -3
# abc1234 feat: login page          ← Commit sai ⚠️
# def5678 docs: update readme
# ghi9012 chore: initial setup

# Bước 3: Reset soft - xóa commit nhưng giữ code trong Staging Area
git reset --soft HEAD~1
# ⚠️ Ý nghĩa: Quay lại 1 commit trước
# - Commit bị xóa ✅
# - Code vẫn lưu (trong Staging Area) ✅
# Nếu có 2 commit sai: git reset --soft HEAD~2
# Nếu có 3 commit sai: git reset --soft HEAD~3

# Bước 4: Tạo feature branch (code vẫn trong Staging Area)
git checkout -b feature/login-page
# Vì code đã add staging area nên khi chuyển nhánh thì code sẽ chuyển qua nhánh đó
# ✅ Code vẫn nguyên vẹn, sẵn sàng commit

# Bước 5: Commit và push trên feature branch
git commit -m "feat: login page"
git push -u origin feature/login-page #Push feature lên GitHub

# Bước 7: Quay lại develop (lúc này đã sạch)
git checkout develop
# ✅ Develop đã tự động sạch (vì reset soft rồi checkout)

# Kiểm tra
git log --oneline -3
# def5678 docs: update readme       ← Commit sai đã bị xóa ✅
# ghi9012 chore: initial setup
```

✅ **Xong!** Giờ:
- `develop` ở local đã sạch
- `feature/login-page` có code của bạn
- Tạo PR trên GitHub: `develop ← feature/login-page`

---

