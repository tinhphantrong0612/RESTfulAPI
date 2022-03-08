# Các ràng buộc kiến trúc  
REST định nghĩa **6 ràng buộc kiến trúc** quy định một RESTful API.  
## 1. Uniform Interface  
Mỗi API cần gắn với một tài nguyên cụ thể, duy nhất.  
Mỗi tài nguyên không nên quá lớn và chứa tất cả thông tin. Thay vào đó, tài nguyên sẽ chứa các liên kết, cho phép truy cập tới các tài nguyên liên quan thông qua liên kết đó, tương tự như quan hệ giữa các bảng trong cơ sở dữ liệu.  
Các tài nguyên trong hệ thống nên làm theo một quy chuẩn, ví dụ như cách đặt tên, định dạng đường dẫn, định dạnh dữ liệu,....  
## 2. Client-Server  
Client và Server phải có khả năng phát triển độc lập mà không phụ thuộc lẫn nhau.  
Giữa chúng giao tiếp qua interface, miễn là interface không đổi, thì việc thay thế Client hay Server là điều bình thường.  
Client chỉ cần biết URI của tài nguyên.  
## 3. Stateless  
Server không lưu lại thông tin gì về HTTP request của client. Mỗi request sẽ là một request mới, không phiên làm việc, không lịch sử.  
Client chịu trách nhiệm quản lý trạng thái của ứng dụng. Một khi client đã đăng nhập thành công, thì mỗi request phải đảm bảo đầy đủ thông tin - bao gồm cả authentication và authorization.  
Lợi ích:  
- Scaling API tới hàng triệu người dùng đồng thời bằng cách triển khai trên nhiều server, server cũng không cần lưu lại thông tin session, cải thiện tốc độ.  
- Giúp API ít phức tạp - Loại bỏ toàn bộ những logic liên quan tới trạng thái phía server.  
- Dễ cache.  
## 4. [Cacheable](https://github.com/tinhphantrong0612/RESTfulAPI/blob/main/Caching.md)  
Caching dữ liệu trở nên quan trọng đối với hiệu năng của ứng dụng, bằng cách giảm các tương tác giữa client và server.  
Tài nguyên cần chỉ ra rằng bản thân có thể cache được hay không.  
## 5. Layered System  
Kiến trúc tổng hợp từ các tầng phân cấp bằng cách ràng buộc hành vi của thành phần.  
Các tầng chỉ có thể tương tác với tầng trực tiếp, và tương tác thông qua các interface, cho phép thay thế các tầng.  
Một tầng không thể biết được bản thân đang kết nối trực tiếp hay chỉ là một tầng trung gian.  
## 6. Code on demand (optional)  
REST cho phép client mở rộng về chức năng bằng cách tải xuống và thực thi mã nguồn dưới dạng applet hay script.  
