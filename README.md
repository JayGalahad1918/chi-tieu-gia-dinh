# Chi tiêu nhà

App web nhỏ để chia tiền chi tiêu chung trong căn hộ: tiền nhà, điện nước, internet, đi chợ… Mọi khoản chia đều cho các thành viên, cuối tháng app tính ai cần chuyển khoản cho ai.

## Tính năng
- **Thành viên**: thêm, sửa, xoá, chọn màu.
- **Khoản định kỳ**: nhập một lần, tự có mỗi tháng. Mỗi tháng tick hoặc bỏ tick, sửa số tiền hay người trả riêng cho tháng đó.
- **Khoản phát sinh**: nhập tay. Số tiền gõ kiểu `250k`, `1tr5`, `3.500.000` đều được.
- **Đọc ảnh chụp Messenger** bằng Claude API: app trích các khoản chi, bạn xem lại rồi mới lưu.
- **Chi phí AI**: ghi lại token input, output, model của từng lần gọi, quy ra tiền, và bảng dự trù chi phí hằng tháng cho từng model.
- **Tổng kết tháng**: ai đã chi bao nhiêu, phần phải chịu, và danh sách chuyển khoản đã gộp cho ít lần nhất. Có nút sao chép để dán vào nhóm chat.
- **Sao lưu**: xuất và nhập file JSON.

## Dữ liệu
- Dữ liệu lưu trong trình duyệt (localStorage) trên máy đang dùng.
- Tuỳ chọn **Lưu trên Neon** (Cài đặt): dán chuỗi kết nối Neon, app tự tạo bảng `chi_tieu_nha` và lưu toàn bộ dữ liệu thành một dòng (cột `data` kiểu jsonb). Mỗi lần sửa sẽ tự lưu lên; mở app hoặc quay lại tab sẽ tự tải bản mới. Nếu hai máy cùng sửa lúc chưa đồng bộ, app hỏi giữ bản nào.
- Chuỗi kết nối Neon và API key Claude chỉ lưu trong trình duyệt máy đang dùng: không nằm trong code, không lên GitHub, API key không được gửi lên Neon.
- File sao lưu không chứa API key.

## Chạy trên GitHub Pages
1. Vào **Settings → Pages** của repo.
2. Ở **Build and deployment**, chọn **Deploy from a branch**, nhánh `main`, thư mục `/ (root)`.
3. Đợi một lát, app có ở `https://<tên-github>.github.io/chi-tieu-gia-dinh/`.

Trên điện thoại, mở link bằng Chrome rồi chọn **Thêm vào màn hình chính** để dùng như app.
