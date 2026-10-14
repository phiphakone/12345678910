# ລົງທະບຽນກິລາວັນຊາດລາວ

Website đăng ký đội thể thao bằng tiếng Lào cho sinh viên Lào tại Đại học Hạ Long.

## Các tệp

- `index.html`: biểu mẫu đăng ký và khu vực quản trị chỉ mở sau khi đăng nhập.
- `firestore.rules`: cho phép gửi đăng ký công khai, nhưng chỉ tài khoản quản trị được xem danh sách và thông tin sinh viên.

## Bật đăng nhập quản trị và lưu đăng ký

Trong Firebase Console của dự án `the-thao-quoc-khach`:

1. Mở Authentication → Sign-in method và bật nhà cung cấp Email/Password.
2. Mở Authentication → Users → Add user. Tạo tài khoản với email quản trị cố định `sports-admin@the-thao-quoc-khach.firebaseapp.com` và tự đặt mật khẩu. Không gửi hoặc ghi mật khẩu vào mã nguồn.
3. Mở Firestore Database → Rules, dán tệp `firestore.rules` và bấm Publish.
4. Đảm bảo Firestore Database đã được tạo.

Trên website, khu vực quản trị chỉ hỏi mật khẩu. Email quản trị được dùng nội bộ để Firebase xác thực; Firestore Rules chỉ cho email đó đọc dữ liệu. Mọi người vẫn có thể gửi biểu mẫu, nhưng không được xem, sửa hoặc xóa danh sách.

## GitHub Pages

Website được xuất bản từ nhánh `main`, thư mục gốc. Firebase SDK tải từ CDN, cần kết nối Internet. Các đăng ký được lưu trong collection `registrations`.
