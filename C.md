# C. Cấu hình docker compose:

## 1. Tạo thư mục: ~/myapp
### Do thư mục myapp đã tạo trước đó giờ chuyển sang bước tiếp theo

## 2. Chuyển vào trong thư mục ~/myapp
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/0ce382c7-aef9-484c-8194-aef2ad420263" />

## 3. Tạo thư mục: ./myweb
<img width="1907" height="1080" alt="image" src="https://github.com/user-attachments/assets/61434804-b08b-4945-87f8-44221ab6a1b0" />

## 4. Tạo file ./myweb/index.html (với nội dung là thông tin cá nhân của em)
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/6abb13a6-ee31-4f69-af6f-bdcf90c85b5f" />

## 5. Tạo file docker-compose.yml để nó sẽ có các dịch vụ sau:
### Khai báo sử dụng nodered/node-red, cổng 1880, dữ liệu nằm tại thư mục ./nodered
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/abc21dbc-8ac4-47eb-969d-546bf15c04e7" />

### Khai báo sử dụng nginx, cổng 80, cấu hình trong file ./nginx/nginx.conf
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/8bc70fee-53aa-4240-902d-f8bdd1c52ba9" />

### Mount thư mục ./myweb thành thư mục /myweb trong nginx
### Mount file ./nginx/nginx.conf vào file /etc/nginx/nginx.conf trong nginx
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/f86fcb46-f8bd-40db-b530-5b250cbed846" />

## 6. Edit file ./nginx/nginx.conf để:
### Cấu hình web server cổng 80 ,server_name là sub-domain (sub-domain tuỳ ý của em)
<img width="1919" height="1080" alt="image" src="https://github.com/user-attachments/assets/0b962fcc-58ce-4407-83be-71df348febf0" />
### location / trỏ tới root là thư mục /myweb
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/1f08dc30-50bc-40d9-9cc7-087cacd1e056" />

### location /api dùng proxy_pass trỏ tới 1 (hoặc nhiều) node http_in của nodered
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/42cdb088-edb4-4307-a049-d136cc7b72a0" />
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/ea8e54a7-d46d-4522-8849-2fda510cde69" />
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/e2f29ce1-cd35-49e8-8512-723632381794" />
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/35514305-d6ca-4aa3-8e54-da595575316d" />

## 7. Edit file ./nodered/settings.js để nodered bắt buộc đăng nhập
### Chạy docker-compose lần đầu để Node-RED tự sinh file cấu hình trong thư mục ./nodered, sau đó mới tiến hành sửa settings.js và restart lại container
<img width="1859" height="1080" alt="image" src="https://github.com/user-attachments/assets/4367c181-cf9c-4ce6-b2f3-a87f404d6839" />
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/4fc0e003-5daf-4350-ad2f-c03849994cc8" />


