# CONTRIBUTING GUIDE

## 1. Mục đích
Tài liệu này quy định **quy trình và nguyên tắc làm việc nhóm** nhằm đảm bảo dự án được phát triển thống nhất, dễ bảo trì và hạn chế xung đột source code.

---

## 2. Quy tắc chung
- Mọi thành viên phải tuân thủ Git workflow của nhóm  
- Không push code trực tiếp lên nhánh main và develop  
- Mỗi chức năng phải được phát triển trên một nhánh riêng  
- Mọi thay đổi quan trọng phải thông qua Pull Request  

---

## 3. Git Workflow sử dụng trong dự án

### 3.1. Các nhánh chính
- main: nhánh ổn định, dùng cho demo và bảo vệ đồ án  
- develop: nhánh phát triển chính  
- feature/*: nhánh phát triển chức năng  

---

## 4. Quy trình làm việc chuẩn

### Bước 1: Cập nhật code mới nhất
Chuyển về develop và pull code (bash):  
git checkout develop  
git pull  

### Bước 2: Tạo nhánh feature
Tạo nhánh mới cho chức năng đang làm (bash):  
git checkout -b feature/ten-chuc-nang  

Ví dụ:  
feature/login  
feature/user-management  

---

### Bước 3: Commit code
Sau khi hoàn thành một phần công việc:

Thêm file vào staging (bash):  
git add .  

Commit code (bash):  
git commit -m "feat: implement login feature"  

---

### Bước 4: Push và tạo Pull Request
Push branch lên GitHub (bash):  
git push origin feature/ten-chuc-nang  

Tạo Pull Request từ feature branch vào develop trên GitHub.

---

## 5. Quy ước commit message

Cấu trúc commit:  
type: mô tả ngắn gọn  

Các type được sử dụng:
- feat: thêm chức năng mới  
- fix: sửa lỗi  
- ui: thay đổi giao diện  
- refactor: tối ưu hoặc tổ chức lại code  
- docs: cập nhật tài liệu  

Ví dụ:
- feat: add RFQ creation API  
- ui: update admin dashboard layout  

---

## 6. Quy định về Pull Request
Mỗi Pull Request cần:
- Mô tả ngắn gọn chức năng đã thực hiện  
- Đảm bảo code không bị lỗi  
- Không chứa file bị ignore (.env, node_modules, target, …)  

---

## 7. Phân công và phối hợp
- Không chỉnh sửa code của thành viên khác khi chưa trao đổi  
- Thông báo cho nhóm khi làm các thay đổi ảnh hưởng lớn  
- Ưu tiên giao tiếp qua nhóm chat hoặc GitHub Issues  

---

## 8. Code Style & Chất lượng
- Viết code rõ ràng, dễ đọc  
- Đặt tên biến, hàm có ý nghĩa  
- Hạn chế hard-code  
- Comment các đoạn logic quan trọng  

---

## 9. Báo lỗi và đề xuất
- Sử dụng GitHub Issues để báo lỗi hoặc đề xuất cải tiến  
- Mô tả rõ vấn đề và cách tái hiện lỗi  

---

## 10. Cam kết
Mỗi thành viên khi tham gia dự án đồng ý tuân thủ các quy định trong tài liệu này nhằm đảm bảo tiến độ và chất lượng đồ án.
