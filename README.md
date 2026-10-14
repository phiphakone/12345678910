# ລົງທະບຽນກິລາວັນຊາດລາວ

Website đăng ký đội thể thao bằng tiếng Lào cho sinh viên Lào tại Đại học Hạ Long.

## Các tệp

- `index.html`: website đăng ký, dùng được như trang GitHub Pages.
- `firestore.rules`: quy tắc Firestore chỉ cho phép gửi đăng ký; không công khai đọc, sửa hoặc xóa thông tin sinh viên.

## Bật lưu đăng ký vào Firebase

1. Mở Firebase Console của dự án `the-thao-quoc-khach`.
2. Vào Firestore Database → Rules.
3. Dán nội dung `firestore.rules` và bấm Publish.
4. Đảm bảo đã tạo Firestore Database trong dự án.

Quy tắc này cho phép biểu mẫu gửi dữ liệu công khai nhưng chặn đọc dữ liệu. Muốn xem danh sách đội, cần bổ sung đăng nhập quản trị và quy tắc đọc dành riêng cho tài khoản quản trị trước khi xây trang quản lý.

## Đưa website lên GitHub Pages

1. Trong repository, mở Settings → Pages.
2. Chọn triển khai từ nhánh `main`, thư mục `/(root)`, rồi Save.
3. Đợi GitHub Pages hoàn tất và mở đường dẫn website được hiển thị tại trang Pages.

Website tải Firebase SDK từ CDN, nên cần kết nối Internet. Dữ liệu đăng ký được gửi vào collection `registrations` của Firestore.
