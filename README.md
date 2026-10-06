# Schedule Admin local — HTML thuần

Mở `index.html` trực tiếp trong trình duyệt hoặc qua localhost. Không có đăng nhập, email, mật khẩu, Node.js, npm hoặc server riêng. CSS/JS đã nhúng trong một file. Không sửa folder Schedule-demo.

## Kết nối dữ liệu

Trang dùng cùng project Supabase `mcilqfmkchoktjsltiuk` với Schedule-demo. Schema hiện tại chỉ cho publishable/anon key đọc sự kiện đã xuất bản, nên CRUD và xem bản nháp cần legacy **service_role JWT key**.

1. Vào Supabase → Project Settings → API Keys → Legacy API Keys, sao chép `service_role` JWT key của project này.
2. Mở `index.html`, dán khóa vào ô cấu hình và bấm **Kết nối dữ liệu**. Không cần tạo tài khoản Auth hoặc chạy SQL bổ sung.

Khóa chỉ giữ trong bộ nhớ tab, không lưu trong HTML/localStorage. Reload hoặc Ngắt kết nối sẽ xóa khóa. Không dùng publishable key hoặc `sb_secret_…` (secret API key không hỗ trợ gọi trực tiếp từ browser). Trang chỉ cho phép kết nối khi mở qua file:// hoặc localhost. Không đưa bản admin có khóa lên hosting công khai; service_role có toàn quyền dữ liệu của project.

## Chức năng

- CRUD sự kiện, loại, ngày/giờ, địa điểm, nguồn, bản đồ, mô tả, ghi chú, topic, keyword, thứ tự.
- CRUD hashtag theo nền tảng, link, ảnh kèm caption, tên file, Drive File ID, thứ tự và ảnh bìa.
- Lưu folder Drive công khai cho Schedule-demo đọc gallery theo cơ chế hiện tại; không upload/sync Drive.
- Bật/tắt xuất bản, tìm kiếm, lọc bản nháp và xóa cascade dữ liệu con.

Lưu sự kiện trước, rồi lưu riêng từng hashtag/link/ảnh. Đổi ảnh bìa: bỏ chọn/lưu ảnh cũ trước khi chọn/lưu ảnh mới. Các mục lưu độc lập. URL `assets/…` giữ nguyên cho Schedule-demo; ưu tiên ảnh HTTPS nếu dùng chung.

Đã kiểm tra cú pháp JavaScript. Chưa kiểm thử CRUD thật vì chưa có khóa service_role.
