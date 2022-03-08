# Compression  
REST API có thể trả về đại diện tài nguyên dưới nhiều dạng như XML, JSON, HTML, hay text. Mọi định dạng đều có thể nén lại để giảm tải băng thông trong mạng.  
HTTP là giao thức phổ biến nhất dùng trong REST, và có cung cấp một số header liên quan tới nén.  
## 1. `Accept-Encoding`  
Khi gửi request, client thêm vào `Accept-Encoding` cho biết loại thuật toán nén nào client hiểu.  
Hai giá trị cơ bản là **compress** và **gzip**.  
Khi đó server phản hồi với gói tin được mã hóa với thuật toán, nếu không thể trả về theo quy định của `Accept-Encoding`, server nên trả về một response báo lỗi với status code **406 (Not Acceptable)**.  
## 2. `Content-Encoding`  
Nếu hiểu được một trong các thuật toán nén từ `Accept-Encoding`, server sử dụng để nén trước khi gửi response về cho client.  
Khi đó, Server thêm vào một header `Content-Encoding` chỉ ra response được nén bằng thuật toán nào, và thuật toán này phải là một trong số các thuật toán trong `Accept-Encoding` bởi request.  
Request cũng có thể gửi tới server với header `Content-Encoding`, đặc biệt trong `POST`. Nếu server không hỗ trợ, server sẽ phản hồi với status code **415(Unsupported Media Type)**.  
Phần lớn trình duyệt hiện tại sẽ yêu cầu nén mặc định.  
