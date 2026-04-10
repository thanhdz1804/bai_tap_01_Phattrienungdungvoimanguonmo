## 1. Tại sao dùng Nginx mà không trỏ thẳng Node-RED?
Ban đầu em nghĩ có thể trỏ trực tiếp vào Node-RED cho đơn giản. Tuy nhiên khi làm thì em thấy cách này chỉ phục vụ được một service. Khi sử dụng Nginx làm reverse proxy, em có thể định tuyến đến nhiều service khác nhau và hệ thống linh hoạt hơn.

## 2. Mount file và mount thư mục khác nhau như thế nào?
Trong quá trình làm, em hiểu rằng mount file là gắn một file cụ thể (ví dụ nginx.conf), còn mount thư mục là gắn toàn bộ thư mục (ví dụ thư mục web). Hai cách này dùng cho các mục đích khác nhau.

## 3. Nếu thay đổi index.html thì web có đổi ngay không?

Khi em thử thay đổi file index.html trên máy Ubuntu thì nội dung web thay đổi ngay. Vì Docker mount trực tiếp thư mục từ máy host nên dữ liệu được cập nhật theo thời gian thực.

## 4. restart: always / unless-stopped để làm gì?

Em sử dụng các tùy chọn này để container tự khởi động lại khi bị lỗi hoặc khi hệ thống khởi động lại. always sẽ luôn chạy lại, còn unless-stopped thì không chạy lại nếu em chủ động dừng.

## 5. Khai báo network chung và lợi ích

Sau khi cấu hình, em thấy việc dùng chung một network giúp các container giao tiếp với nhau bằng tên service (như nginx, nodered) thay vì IP, giúp hệ thống dễ quản lý hơn.

## 6. Đưa token vào .env và .gitignore

Trong quá trình làm, em nhận thấy token là thông tin nhạy cảm. Nếu để trong code và đưa lên GitHub sẽ dễ bị lộ, nên em đưa vào file .env và thêm vào .gitignore để đảm bảo bảo mật.

## 7. Tại sao dùng :ro khi mount nginx.conf?

Em sử dụng :ro để container chỉ có quyền đọc file cấu hình, không thể chỉnh sửa, giúp tránh lỗi và tăng bảo mật.

## 8. Cloudflare Tunnel có cần mở port không?

Khi sử dụng Cloudflare Tunnel, em không cần mở port vì kết nối được thiết lập từ bên trong ra ngoài, giúp hệ thống an toàn hơn.
