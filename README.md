# ESTA — Đánh giá CLDV & Chế tài nhà thầu

Web lập biên bản vi phạm, duyệt biên bản, tổng hợp khấu trừ phí dịch vụ tháng, thông báo nhà thầu (PDF + nội dung email) và dashboard tái phạm cho dịch vụ An ninh – Vệ sinh tại L'MAK 68, Lite The Venture, 127 Hồng Hà, 130 Hồng Hà.

- **Giao diện:** GitHub Pages — https://billpham96.github.io/esta-danh-gia-cldv/
- **Dữ liệu chung:** Google Sheet của Quản lý vận hành + Google Apps Script (file `Code.gs` — lưu riêng, **không** đưa lên GitHub vì chứa mật khẩu). Mọi máy đăng nhập đều thấy cùng dữ liệu; web tự làm mới mỗi 30 giây (hoặc bấm **Làm mới**).
- **Luồng biên bản:** BQL lưu nháp → **Gửi admin duyệt** → admin nhận ngay (mục **Duyệt biên bản**, email thông báo) → **Duyệt chính thức** hoặc **Từ chối** kèm lý do → BQL sửa và gửi lại. Admin có thể duyệt thẳng biên bản do mình lập và **Mở lại để sửa** biên bản đã chính thức. Chỉ biên bản chính thức được tính vào tổng hợp và khấu trừ.
- **Phân quyền** kiểm tra trên máy chủ: tài khoản dự án chỉ đọc/ghi dữ liệu tòa nhà mình, không duyệt được, không sửa được biên bản đã gửi; chỉ admin sửa danh mục hợp đồng & mức phạt.
- **Chống ghi đè:** nếu biên bản vừa được người khác cập nhật, web báo và tải bản mới nhất thay vì ghi đè. Số biên bản / số thông báo được máy chủ kiểm tra không trùng.
- **Tài khoản & mật khẩu** khai báo trong `Code.gs` (mục `CONFIG.ACCOUNTS`), không nằm trong web công khai. Đổi mật khẩu: sửa `Code.gs` → Triển khai → Quản lý các bản triển khai → Phiên bản mới.
- **Dữ liệu cũ** (bản web lưu trên trình duyệt từng máy): khi đăng nhập trên máy còn dữ liệu cũ, web hiện nút **Đưa lên hệ thống chung**. Có thể dùng **Dữ liệu → Nhập file** cho file sao lưu .json cũ.
- Danh mục lỗi & mức phạt trích từ hợp đồng; Quản lý vận hành chỉnh sửa trong mục **Hợp đồng**.
