# CONTRIBUTING GUIDE

Quy tắc & tiêu chuẩn làm việc cho tất cả thành viên dự án.

---

## 1. Nguyên tắc chung

- ✅ Mọi thành viên tuân thủ Git workflow
- ✅ Mọi thay đổi quan trọng thông qua Pull Request (PR)
- ❌ Không push trực tiếp lên `main` hoặc `develop`
- ❌ Không force push
- ❌ Mỗi branch chỉ làm một nhiệm vụ

---

## 2. Git Workflow

### Các nhánh chính

- **main ← develop** (chỉ merge khi demo/bảo vệ đồ án)
- **develop ← feature/** (nhánh phát triển chính, default branch)
- **feature/** (tạo feature từ develop, PR → merge vào develop)

### Luồng cơ bản

```
develop → feature/ten-chuc-nang → Pull Request → Review → develop → main
```

**Chi tiết từng bước:** Xem [GitChecklist.md](GitChecklist.md)

---

## 3. Quy ước Commit Message

**Cấu trúc:**

```
type: mô tả ngắn gọn
```

**Các loại (type) được sử dụng:**

- `feat` – Thêm chức năng mới
- `fix` – Sửa lỗi
- `ui` – Thay đổi giao diện
- `refactor` – Tối ưu / tổ chức lại code
- `docs` – Cập nhật tài liệu
- `test` – Thêm/cập nhật test

**Ví dụ:**

```
feat: implement user authentication API
fix: resolve login validation error
ui: redesign product card component
refactor: extract utility functions
docs: update API documentation
```

**Lưu ý:**

- Mô tả ngắn gọn, rõ ý (< 50 ký tự)
- Không viết quá dài một dòng commit
- Commit liên quan đến một chức năng cụ thể

---

## 4. Pull Request (PR)

### Yêu cầu bắt buộc

- [ ] **Tiêu đề rõ ràng** – mô tả chức năng đã làm
- [ ] **Mô tả chi tiết** – phần hệ thống bị ảnh hưởng
- [ ] **Code đã test** – không có lỗi hiển thị
- [ ] **Không chứa file bị ignore** – `.env`, `node_modules/`, `target/`, v.v.
- [ ] **1-2 reviewer** – ít nhất một người review trước merge

### Mẫu mô tả PR

```markdown
## 📝 Mô tả

Chức năng được thêm / vấn đề được sửa.

## 🔍 Kiểm tra

- [ ] Chạy test thành công
- [ ] Không có console error/warning
- [ ] Đã test trên múi trình duyệt

## 📋 Liên kết

Liên kết issue hoặc ticket liên quan (nếu có).
```

### Quy trình review

1. Tạo PR từ branch feature vào develop
2. Assign reviewer
3. Đợi review comment
4. Sửa code nếu có yêu cầu → push tiếp
5. Approve → merge khi ready

---

## 5. Code Style & Chất lượng

### Frontend (React + TypeScript)

- ✅ Sử dụng **TypeScript** cho type safety
- ✅ Tuân thủ **ESLint** config của dự án
- ✅ Component names: PascalCase (vd: `UserCard.tsx`)
- ✅ Function names: camelCase (vd: `getUserData()`)
- ✅ Không hard-code giá trị – dùng config/constants
- ✅ Comment component phức tạp

**Ví dụ cấu trúc component:**

```typescript
/**
 * UserCard - Hiển thị thông tin người dùng
 * @param {User} user - Dữ liệu người dùng
 */
export const UserCard: React.FC<{ user: User }> = ({ user }) => {
  return <div>{user.name}</div>;
};
```

### Backend (Spring Boot + Java)

- ✅ Tuân thủ **Java naming conventions**
- ✅ Class names: PascalCase
- ✅ Method names: camelCase
- ✅ Không magic numbers – dùng constants
- ✅ Comment business logic phức tạp
- ✅ Viết unit tests cho service layer

---

## 6. Phối hợp nhóm

- 📢 **Thông báo** khi làm các thay đổi ảnh hưởng lớn
- 💬 **Trao đổi** trước qua chat/Discord nếu cần
- 👥 **Không chỉnh sửa** code của thành viên khác khi chưa xin phép
- 🔔 **Notify** reviewer qua comment nếu PR bị stuck

---

## 7. Báo lỗi & Đề xuất

### Sử dụng GitHub Issues

1. Mô tả **rõ ràng** vấn đề (title + description)
2. **Cách tái hiện** lỗi (reproduction steps)
3. **Expected vs Actual** behavior
4. **Attachment** (screenshot, log, etc.)

**Ví dụ:**

```
Title: Login form không submit khi password chứa ký tự đặc biệt

Description:
- Mô tả chi tiết vấn đề
- Step to reproduce:
  1. Vào trang login
  2. Nhập password với "@#$"
  3. Click submit

Expected: Form submit thành công
Actual: Submit button disabled
```

---

## ⚠️ Ghi chú quan trọng

- 📦 Không push `node_modules/`, `target/`, `.env` lên GitHub
- 🔐 Không commit credentials, API keys, passwords
- 📝 Luôn cập nhật `.gitignore` khi thêm thư mục mới
- 🔄 Luôn pull develop trước khi tạo feature branch

---

## 📚 Tài liệu thêm

- **Setup chi tiết:** [INSTALL.md](INSTALL.md)
- **Checklist thao tác Git:** [GitChecklist.md](GitChecklist.md)
- **README Overview:** [README.md](README.md)
