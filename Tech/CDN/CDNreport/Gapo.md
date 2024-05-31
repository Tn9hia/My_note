## 1. Mô tả vấn đề
![[Screenshot 2024-05-10 at 14.08.19.png]]
- KH triển khai sử dụng CDN ở domain: https://app.gapowork.vn Tuy nhiên khi triển khai không CDN thì truy cập bình thường nhưng có CDN thì lại trả về status code **404-Not Found**
## 2. Quá trình xử lý
#### Nguyên nhân vấn đề
- Từ server CDN khi truy cập về origin có nhiều virtual host, nếu không khai báo defaul host hoặc CDN chưa cấu hình [[HTTP header|Host header]] thì khi CDN gọi về origin không biết sẽ vào virtual host nào để lấy resource nên trả về 404
#### Hướng xử lý
- Thực hiện cấu hình thêm Host header sau trên CDN:
```
Host:app.gapowork.vn
```
## 3. Bài học
- Trong quá trình debug nên kiểm tra origin của khách hàng. Có thể sử dụng lệnh sau để kiểm tra origin có trả về đúng thông tin hay không.
```
curl <ip-address> -vk
```
>Bình thường khi gọi tới origin mà  không thêm host header sẽ vào defaul host. Nếu không có defaul host sẽ trả về 404 với câu lệnh trên.

