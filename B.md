# B. Cài đặt Ubuntu + Docker
# Cài đặt hệ điều hành Ubuntu 24.04.4 LTS
- Sử dụng một trong các công cụ để giả lập: HyperV (có sẵn của windows), VirutualBox (Miễn phí), VM_Ware (bản quyền)
Download file iso để cài đặt.
Cấu hình mạng trong Ubuntu (và công cụ giả lập) để cho phép truy cập SSH vào Ubuntu từ cmd của windows
<img width="1115" height="643" alt="image" src="https://github.com/user-attachments/assets/b5d0fe19-a43e-4252-9f4d-3af27b82e44c" />
## 1 Tìm hiểu các lệnh cơ bản của ubuntu
## 2 Các lệnh cần tìm hiểu:
## Liệt kê các file trong thư mục: ls
Tạo thư mục: mkdir nameFolder
Chuyển thư mục làm việc: cd path
Copy file: cp file_nguồn path/file_đích
Thay đổi quyền thao tác file: sudo chmod xxx filename
<img width="523" height="242" alt="image" src="https://github.com/user-attachments/assets/20c10d78-4c11-444c-bf11-2deb55c5a8ff" />
Edit file: sudo nano tenfile
<img width="1114" height="647" alt="image" src="https://github.com/user-attachments/assets/179e9ab8-f9b6-468e-b06e-69228a33c25d" />
CTRL+o : lưu nội dung sau khi edit
CTRL+x : thoát edit file
Xem ip của máy ubuntu: ip -4 addr
<img width="1097" height="643" alt="image" src="https://github.com/user-attachments/assets/36693124-cdce-4fab-bd3b-9a9842a85de3" />
## 3 Cài đặt docker cho Ubuntu
<img width="504" height="65" alt="image" src="https://github.com/user-attachments/assets/9c9da2df-74fe-46b8-b756-3d88c9502429" />
## 4 Kiểm tra phiên bản docker vừa cài đặt, kiểm tra phiên bản của docker compose
<img width="1100" height="635" alt="image" src="https://github.com/user-attachments/assets/c49897cc-e1b9-4e3c-a567-a5a1ca819710" />
## 5 Cấu hình để docker chạy mà không cần tiền tố sudo
<img width="1105" height="638" alt="image" src="https://github.com/user-attachments/assets/3b9028b6-20fc-4193-8d9e-26601f51ea7a" />
## 6 Tìm hiểu tập lệnh của docker và docker compose
docker ps            # xem container đang chạy
docker ps -a         # xem tất cả container
docker images        # xem danh sách image
docker run           # chạy container
docker stop <id>     # dừng container
docker rm <id>       # xóa container
## 7Đảm bảo tường lửa trên Ubuntu đã cho phép các cổng 80, 1880, 9630 (Lệnh: sudo ufw allow ...)
<img width="1105" height="639" alt="image" src="https://github.com/user-attachments/assets/1c9e9b22-d400-4540-b80b-016f7d985834" />
