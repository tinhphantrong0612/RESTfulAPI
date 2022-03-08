# Idempotent  
Trong ngữ cảnh REST API, khi lặp lại một request nhiều lần mà có hiệu ứng tương tự như thực hiện request đó một lần, thì REST API đó gọi là lũy đẳng.  
Khi thiết kế REST API, cần phải hiểu rõ client có thể gửi các request lặp, dù là cố ý hay vô tình (do timeout, vấn đề mạng).  
API cần phải xử lý được những request này.  
# Tính lũy đẳng với các phương thức HTTP  
## 1. HTTP `POST` không lũy đẳng  
Thông thường, `POST` API dùng để tạo mới tài nguyên trên server.  
Và khi thực hiện n lần, n tài nguyên mới được thêm vào.  
Khi đó, việc hạn chế tính không lũy đẳng là cần thiết với việc validate các `POST` request trước khi thêm mới tài nguyên.  
## 2. HTTP `GET`, `HEAD`, `OPTIONS` và `TRACE` lũy đẳng  
Những phương thức trên không thay đổi trạng thái tài nguyên trên server.  
## 3. HTTP `PUT`  
Thông thường, `PUT` API dùng để cập nhật tài nguyên.  
Khi gọi n lần `PUT`, lần đầu tiên là cập nhật tài nguyên, n-1 lần tiếp theo cũng vẫn là cập nhật tài nguyên đó.  
## 4. HTTP `DELETE`  
Khi xóa với định danh tài nguyên (xóa bằng ID), thực hiện một lần, tài nguyên bị xóa. Thực hiện n lần, tài nguyên bị xóa, và n-1 lần trả về **404 (Not Found).** hoặc **204 (No Content)**  
Đôi khi có những API kiểu `DELETE item/last`, lúc này `DELETE` không còn lũy đẳng  
**Tính lũy đẳng còn phụ thuộc vào cách cài đặt API.**
