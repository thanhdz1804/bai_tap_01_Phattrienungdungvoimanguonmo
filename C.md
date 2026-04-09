# C. Cấu hình docker compose:
1. Tạo thư mục: ~/myapp
<img width="1099" height="631" alt="image" src="https://github.com/user-attachments/assets/03472ac2-2238-4f6f-a779-a44ac27782b0" />
2. Chuyển vào trong thư mục ~/myapp
4. Tạo thư mục: ./myweb
6. Tạo file ./myweb/index.html (với nội dung là thông tin cá nhân của em)
<img width="1098" height="634" alt="image" src="https://github.com/user-attachments/assets/159e1c1e-7ec0-4d2f-938c-a05875e6d4b0" />
7. Tạo file docker-compose.yml để nó sẽ có các dịch vụ sau:
Khai báo sử dụng nodered/node-red, cổng 1880, dữ liệu nằm tại thư mục ./nodered
Khai báo sử dụng nginx, cổng 80, cấu hình trong file ./nginx/nginx.conf
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/c45379c7-0035-4b67-9bcf-4d06d002c169" />
Mount thư mục ./myweb thành thư mục /myweb trong nginx
Mount file ./nginx/nginx.conf vào file /etc/nginx/nginx.conf trong nginx
9. Edit file ./nginx/nginx.conf để:
Cấu hình web server cổng 80
server_name là sub-domain (sub-domain tuỳ ý của em)
location / trỏ tới root là thư mục /myweb
location /api dùng proxy_pass trỏ tới 1 (hoặc nhiều) node http_in của nodered
10. Edit file ./nodered/settings.js để nodered bắt buộc đăng nhập
Chạy docker-compose lần đầu để Node-RED tự sinh file cấu hình trong thư mục ./nodered, sau đó mới tiến hành sửa settings.js và restart lại container

