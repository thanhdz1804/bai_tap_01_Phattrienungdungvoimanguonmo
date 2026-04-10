# G.Triển khai ứng dụng đến End-user
## 1. Trong Cloudflare: Tạo tunnel (đường hầm), chọn loại triển khai cho docker
<img width="1919" height="1080" alt="image" src="https://github.com/user-attachments/assets/65cf8d6e-2191-4b16-8197-8aa180eace15" />
## 2. Convert lệnh docker run ... sang dạng docker compose
<img width="1917" height="1076" alt="image" src="https://github.com/user-attachments/assets/240b7259-745b-49c4-85ad-c490b4ea5e86" />

## 3.Khai báo kết quả convert vào trong file docker-compose.yml
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/8b1395d6-bf25-4b82-9937-1365635b6e42" />

## 4. Chạy lại docker compose
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/6b5e073e-2217-4a3c-b583-6e10f89c3135" />

## 5.Public ứng dụng bằng cách thêm 1 router trỏ tới container đang chạy trong docker, dữ liệu sẽ đi qua tunnel, url dạng sub-domain
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/2afe2aea-401e-45ff-959b-9a9eb8f497c1" />

## Kiểm tra url sub-domain đã hoạt động public cho mọi end-user
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/3df847bb-c54e-4846-9f3d-db416dd136e6" />
<img width="1917" height="1070" alt="image" src="https://github.com/user-attachments/assets/f9c74ed8-8d84-4b8a-a261-39a384efc008" />

