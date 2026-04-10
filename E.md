# E. Triển khai (level test) ứng dụng
## 1. Chuyển vào trong thư mục ~/myapp
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/8aaeaf1e-31e7-450c-ad1f-86b5609f4fa3" />

### 2. Gõ lệnh để docker compose chạy: sẽ run tất cả các service khai báo trong file docker-compose.yml,Lợi ích: Chỉ cần docker-compose up -d là toàn bộ hệ thống (Web + Node-RED + Tunnel) tự chạy,
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/7ca77af6-e3ad-4d12-8285-cc7b079bf51f" />

### 3. Kiểm tra các container đang chạy trong docker, nếu có cái nào bị restart cần tìm lỗi rồi edit lại docker-compose.yml
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/fb17c37d-f5f9-4069-8f16-316c9645bc59" />

### 5. Kiểm tra kiểm thử các service đang chạy độc lập thông qua ip và port của nó: ví dụ mở trình duyệt ip_ubuntu:1880 để check nodered đã chạy chưa
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/19f193e4-b109-4689-b445-04291bb05a8a" />

### 6. Sử dụng nodered: kéo nodered http_in , http_response, function : để tạo api get đơn giản (dùng cho /api proxy_pass của nginx)
<img width="1915" height="1080" alt="image" src="https://github.com/user-attachments/assets/ed4b0ae9-4205-402a-a3b5-5e17ce85c64c" />

<img width="1919" height="1077" alt="image" src="https://github.com/user-attachments/assets/140783de-78fd-46e7-a1bc-cabbe66a1e68" />

### 7. Sửa file ./myweb/index.html : thêm code html+js để sử dụng được api đã khai báo proxy_pass (thực ra là sử dụng nodered http_in hoặc sử dụng service myapi)
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/3fb727f9-5081-41bb-b40b-2bea6c23c0ec" />
