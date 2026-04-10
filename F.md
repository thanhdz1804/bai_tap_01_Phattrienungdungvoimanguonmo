# F. Gỡ lỗi:nếu có lỗi xẩy ra trong quá trình triển khai docker compose up -d
### 1. Kiểm tra nhanh: docker compose ps giúp biết container nào đang chạy xem log, ví dụ: docker logs mynginx docker logs myapi
<img width="1913" height="1078" alt="image" src="https://github.com/user-attachments/assets/2ee73f62-e5bf-4c9a-a656-845631dbdf49" />

### 2. Thêm healthcheck cho myapi trong file docker-compose.yml
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/d0ad9a74-5fa9-411f-97d1-413d5153ddf2" />
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/f0dfc5b9-0761-43e7-98fb-309d41c1b48f" />

healthcheck:
  test: ["CMD", "curl", "-f", "http://localhost:9630"]
### 3. giới hạn resource cho một service: (tránh việc 1 service chiếm quá nhiều ram)
thêm bằng lệnh có sẵn
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/8b05cd65-598c-4799-9575-45454b2e460b" />

### sử dụng lệnh: docker compose stats để quan sát lượng ram sử dụng bởi mỗi service
<img width="1919" height="1080" alt="image" src="https://github.com/user-attachments/assets/465a3718-cc8b-441d-a943-42a1c7da32d8" />


