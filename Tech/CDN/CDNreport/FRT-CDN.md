## 1. Mô tả vấn đề
![[Screenshot 2024-05-10 at 13.29.45.png]]
Khách hàng cấu hình CDN cho 2 domain 
- nonprod-frontend.nhathuoclongchau.com.vn 
- frontedn.nhathuoclongchau.com.vn
Tuy nhiên, sau khi đợi 40p vẫn không thể kết nối và hiện lỗi là **503-Service Unavailable**
## 2. Quá trình xử lý
Khi truy cập dùng giao thức HTTP thì hiện lỗi. Nguyên nhân là do origin đang cấu hình dùng HTTPS-port 443 trong khi request tới origin là HTTP-port 80. Do Origin không thể xử lý request port 80 nên sẽ trả về status code **503-Service Unavailable**

## 3. Bài học rút ra
- Cần cấu hình trỏ về đúng port ở origin server và nên sử dụng IP thay vì domain name.