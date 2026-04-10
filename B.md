# Cài đặt Ubuntu + Docker
## Cài đặt hệ điều hành Ubuntu 24.04.4 LTS

### Sử dụng công cụ để giả lậpVM_Ware (bản quyền)

<img width="1473" height="970" alt="image" src="https://github.com/user-attachments/assets/0c4d3878-0925-4877-8ec5-e08d3cd46ba6" />

### sau đó chọn cấu hình như bình thường cài tài khoản mật khẩu với ubuntu để chuẩn bị bước ssh

Cấu hình mạng trong Ubuntu (và công cụ giả lập) để cho phép truy cập SSH vào Ubuntu từ cmd của windows
<img width="1115" height="643" alt="image" src="https://github.com/user-attachments/assets/b5d0fe19-a43e-4252-9f4d-3af27b82e44c" />

# 1. Tìm hiểu các lệnh cơ bản của 

# 2. Các lệnh cần tìm hiểu:

## - Liệt kê các file trong thư mục: ls

## - Tạo thư mục: mkdir nameFolder

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/a953aa05-42c2-4a36-9e9b-9913cb858591" />

## - Chuyển thư mục làm việc: cd path

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/1d5dbcb4-ed41-49a3-978e-03b6e2193364" />

## - Copy file: cp file_nguồn path/file_đích

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/c1711520-4c71-432f-a9cf-ca464c7aaad1" />

## - Thay đổi quyền thao tác file: sudo chmod xxx filename

<img width="1920" height="1079" alt="image" src="https://github.com/user-attachments/assets/b5e066a8-c0cd-4925-bbcb-79d8b22d752f" />

## - Edit file: sudo nano tenfile

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/40780632-e4c7-4e44-b821-d5e6c7bbd77d" />

CTRL+o : lưu nội dung sau khi edit
CTRL+x : thoát edit file

## - Xem ip của máy ubuntu: ip -4 addr

<img width="1918" height="1080" alt="image" src="https://github.com/user-attachments/assets/a069a858-c6d1-4f2e-8f82-92c1afea3581" />

# 3 Cài đặt docker cho Ubuntu

<img width="1917" height="1080" alt="image" src="https://github.com/user-attachments/assets/e38b2ef0-3f72-42d0-b6d6-f85309ff6d61" />

# 4 Kiểm tra phiên bản docker vừa cài đặt, kiểm tra phiên bản của docker compose

<img width="1919" height="1080" alt="image" src="https://github.com/user-attachments/assets/7bd853cf-6b0e-4174-86ab-f663b92bc8a4" />

# 5 Cấu hình để docker chạy mà không cần tiền tố sudo

<img width="1920" height="1075" alt="image" src="https://github.com/user-attachments/assets/0baf07f5-e150-4e6b-8de1-6da2393aea5e" />

# 6 Tìm hiểu tập lệnh của docker và docker compose

- docker ps            # xem container đang chạy
- docker ps -a         # xem tất cả container
- docker images        # xem danh sách image
- docker run           # chạy container
- docker stop <id>     # dừng container
- docker rm <id>       # xóa container

# 7Đảm bảo tường lửa trên Ubuntu đã cho phép các cổng 80, 1880, 9630 (Lệnh: sudo ufw allow ...)

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/bf111faa-8142-4ee2-9d47-ed89d26adfe3" />

