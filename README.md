# bai_tap_01_Phattrienungdungvoimanguonmo
# Môn: Phát triển ứng dụng với mã nguồn mở-TEE0421
Lớp: 58KTPM
Bài tập 01:
deadline : 23h59 ngày 13 tháng 4 năm 2026.
## A. Đăng ký tên miền xịn cho cá nhân:
## Đăng ký domain xịn (có thể dùng của mắt bão, tên miền *.id.vn đang miễn phí cho mọi công dân việt nam <= 23 tuổi, *.io.vn : giá 30k vnđ/năm)
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/0c74e421-adbd-4699-93b3-42b1230b3d3e" />
### Đăng ký tài khoản cloudflare
<img width="1728" height="1044" alt="image" src="https://github.com/user-attachments/assets/f6920d80-9cd8-4b10-9aa6-be01b0d28ed1" />
Thêm domain đã đăng ký vào trong cloudflare : Nhận 2 dòng namespace
## Nhập 2 dòng namespace của cloudflare vào trong trang quản lý DNS record của tên miền đăng ký 
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/fb3f0de3-44d7-4fd0-9bae-4a4604511489" />
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
Mount thư mục ./myweb thành thư mục /myweb trong nginx
Mount file ./nginx/nginx.conf vào file /etc/nginx/nginx.conf trong nginx
8. Edit file ./nginx/nginx.conf để:
Cấu hình web server cổng 80
server_name là sub-domain (sub-domain tuỳ ý của em)
location / trỏ tới root là thư mục /myweb
location /api dùng proxy_pass trỏ tới 1 (hoặc nhiều) node http_in của nodered
9. Edit file ./nodered/settings.js để nodered bắt buộc đăng nhập
Chạy docker-compose lần đầu để Node-RED tự sinh file cấu hình trong thư mục ./nodered, sau đó mới tiến hành sửa settings.js và restart lại container

D. (Bonus - không bắt buộc)
tạo thư mục ./myapi
tạo file ./myapi/app.py sử dụng Python + Flask để làm gì đó funny
tạo file ./myapi/requirements.txt chứa các thư viện mà app.py sử dụng (theo như app.py ví dụ thì requirements.txt chỉ cần có nội dung: flask)
tạo file ./myapi/Dockerfile để khai báo sử dụng Python 3.9 slim
 # Sử dụng phiên bản Python nhẹ (alpine) để giảm dung lượng image
 FROM python:3.9-slim

 # Thiết lập thư mục làm việc bên trong container
 WORKDIR /app

 # Sao chép file requirements vào và cài đặt thư viện
 COPY requirements.txt .
 RUN pip install --no-cache-dir -r requirements.txt

 # Sao chép toàn bộ mã nguồn vào container
 COPY . .

 # Thông báo container sẽ chạy ở cổng 9630
 EXPOSE 9630

 # Lệnh khởi chạy ứng dụng
 CMD ["python", "app.py"]
Sửa đổi docker-compose để sử dụng myapp (xem phần tham khảo ở dưới)
Sửa đổi nginx/nginx.conf để /api trỏ tới service myapp cổng 9630
E. Triển khai (level test) ứng dụng
Chuyển vào trong thư mục ~/myapp
Gõ lệnh để docker compose chạy: sẽ run tất cả các service khai báo trong file docker-compose.yml
Lợi ích: Chỉ cần docker-compose up -d là toàn bộ hệ thống (Web + Node-RED + Tunnel) tự chạy,

Kiểm tra các container đang chạy trong docker, nếu có cái nào bị restart cần tìm lỗi rồi edit lại docker-compose.yml
Kiểm tra kiểm thử các service đang chạy độc lập thông qua ip và port của nó: ví dụ mở trình duyệt ip_ubuntu:1880 để check nodered đã chạy chưa
Sử dụng nodered: kéo nodered http_in , http_response, function : để tạo api get đơn giản (dùng cho /api proxy_pass của nginx)
Sửa file ./myweb/index.html : thêm code html+js để sử dụng được api đã khai báo proxy_pass (thực ra là sử dụng nodered http_in hoặc sử dụng service myapi)
F. Gỡ lỗi:
nếu có lỗi xẩy ra trong quá trình triển khai docker compose up -d
Kiểm tra nhanh: docker compose ps giúp biết container nào đang chạy xem log, ví dụ: docker logs mynginx docker logs myapi

Thêm healthcheck cho myapi trong file docker-compose.yml
healthcheck:
  test: ["CMD", "curl", "-f", "http://localhost:9630"]
giới hạn resource cho một service: (tránh việc 1 service chiếm quá nhiều ram)
deploy:
  resources:
    limits:
      memory: 512M
sử dụng lệnh: docker compose stats để quan sát lượng ram sử dụng bởi mỗi service
G. Triển khai ứng dụng đến End-user
Trong Cloudflare: Tạo tunnel (đường hầm), chọn loại triển khai cho docker
Convert lệnh docker run ... sang dạng docker compose
Khai báo kết quả convert vào trong file docker-compose.yml
Chạy lại docker compose
Public ứng dụng bằng cách thêm 1 router trỏ tới container đang chạy trong docker, dữ liệu sẽ đi qua tunnel, url dạng sub-domain
Kiểm tra url sub-domain đã hoạt động public cho mọi end-user
Cấu trúc thư mục:
myapp/
├── docker-compose.yml
├── nginx/
│   └── nginx.conf
├── myweb/
│   └── index.html
└── nodered/ (sẽ tự sinh dữ liệu)
│   └── (có nhiều file tự sinh)
│   └── settings.js (file này cần edit để bắt nodered login)
Sơ đồ theo góc nhìn của dev:

Sơ đồ theo góc nhìn ngược lại:

G. Câu hỏi về bài làm?
Tại sao phải dùng Nginx làm Reverse Proxy mà không trỏ thẳng Tunnel vào Node-RED?
Sự khác biệt giữa việc Mount file và Mount thư mục trong Docker là gì?
Nếu thay đổi file index.html ở máy Ubuntu, nội dung trên web có thay đổi ngay không? Tại sao?
docker-compose.yml khai báo các services có phần restart: always hoặc restart: unless-stopped : chúng để làm gì?
Cách khai báo để tất cả các services đều dùng chung 1 network? lợi ích của việc khai báo này là gì? Sửa đổi file docker-compose để tất cả các service đều dùng chung 1 network.
Tìm cách đưa Cloudflare Token vào trong file .env rồi sau đó thêm .env vào file .gitignore trước khi push code lên github. Tại sao nói đây là điều quan trọng về bảo mật mã nguồn?
Tại sao chúng ta nên thêm hậu tố :ro khi mount file cấu hình Nginx?
Khi dùng Cloudflare Tunnel: có cần thiết phải mở cổng cho các service nữa không?
Hướng dẫn làm bài:
sv tự làm trên laptop cá nhân, tự nâng cấp các phần mềm hoặc OS lên phiên bản phù hợp, trang bị cấu hình đủ tải (RAM từ 8GB, ổ cứng SSD or NVME)
quá trình làm: chụp màn hình, paste hình ảnh + gõ text chú thích cho hình ảnh vào readme.md của 1 repo trên github cá nhân, để truy cập public
Mỗi phần ABCDEFG tạo 1 file tương ứng là A.md , B.md .... file README.md chứa link tới các file A.md, B.md, ... để dễ quản lý
Mỗi file cho mỗi phần chứa nội dung đã làm: hình ảnh + text thuyết minh (lặp nhiều lần) cho phần đó.
làm xong tất cả: paste link của repo vào file tổng hợp excel online (làm sau cũng được, vì github ko fake date được)
Tham khảo file trên lớp
./docker-compose.yml :

	 services:
	  myapi:
	    build:
	      context: ./myapi
	      dockerfile: Dockerfile
	    container_name: myapi
	    ports:
	      - "9630:9630"
	    restart: always

	  mynodered:
	    image: nodered/node-red
	    container_name: mynodered
	    restart: unless-stopped
	    ports:
	      - "1880:1880"
	    volumes:
	      # đường dẫn thư mục trên máy của bạn
	      - ./nodered:/data

	  mycloudflared:
	    image: cloudflare/cloudflared:latest
	    container_name: mycloudflared
	    restart: unless-stopped
	    command: tunnel --no-autoupdate run --token <your_token>

	  mynginx:
	    image: nginx
	    container_name: mynginx
	    restart: always
	    ports:
	      - "80:80"
	      - "443:443"
	    volumes:
	      # Ánh xạ thư mục chứa file bài thơ
	      - ./myweb:/myweb:ro
	      # Ánh xạ file cấu hình nginx
	      - ./nginx/nginx.conf:/etc/nginx/nginx.conf:ro
./nginx/nginx.conf :

events {}
http {
	server {
	    listen 80;
	    server_name thotinh.tdh.io.vn;

	    location / {
	        root /myweb;
	        index index.html index.htm;
	        try_files $uri $uri/ =404;
	    }

	    location /api {
	        # 'myapi' là tên container trong docker-compose
	        proxy_pass http://myapi:9630/tinh-vat;
	        proxy_set_header Host $host;
	        proxy_set_header X-Real-IP $remote_addr;
	        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
	        proxy_set_header X-Forwarded-Proto $scheme;
	    }
	}
}
./myapp/app.py :

	from flask import Flask, request, jsonify

	app = Flask(__name__)

	@app.route('/tinh-vat', methods=['GET'])
	def tinh_vat():
	    # Lấy giá trị từ tham số "tien" trên URL
	    tien_input = request.args.get('tien')
	    
	    # Kiểm tra xem người dùng có nhập tiền hay không
	    if tien_input is None:
	        return jsonify({"error": "Vui lòng cung cấp tham số 'tien'"}), 400
	    
	    try:
	        # Chuyển đổi sang kiểu số thực và tính toán
	        so_tien = float(tien_input)
	        ket_qua = so_tien * 1.1
	        
	        return jsonify({
	            "so_tien_goc": so_tien,
	            "thue_vat": "10%",
	            "tong_cong": ket_qua
	        })
	    except ValueError:
	        # Trả về lỗi nếu đầu vào không phải là số
	        return jsonify({"error": "Giá trị 'tien' phải là một con số hợp lệ"}), 400

	if __name__ == '__main__':
	    # Chạy ứng dụng tại cổng 9630
	    app.run(host='0.0.0.0', port=9630)
