# REST (REpresentation State Transfer)  
Phong cách kiến trúc cho hệ thống phân phối hypermedia.  
Như các phong cách kiến trúc khác, REST cũng có những nguyên tắc và ràng buộc.  
Một Web API xây dựng theo phong cách REST gọi là *REST API*.  
## Nguyên tắc của REST  
### Giao diện tiêu chuẩn  
Mỗi API với mỗi tài nguyên. Tài nguyên trong hệ thống chỉ có một URI duy nhất và tài nguyên đó phải cung cấp cách để tìm đến thông tin liên quan.  
### Mô hình client-server  
Client-server được thiết kế và phát triển tách biệt, chỉ giao tiếp với nhau qua API.  
### Stateless  
Không trạng thái: Mỗi request từ client yêu cầu phải chứa đủ thông tin để server xử lý, không thể phụ thuộc vào các phiên làm việc trước hay các request trước.  
Ví dụ với xác thực quyền người dùng:
	- Stateful: Người dùng đăng nhập, server xác nhận và đặt cookie cho client, đồng thời lưu lại thông tin phiên đăng nhập session. Mỗi khi client gửi request, kèm theo cookie, server kiểm tra session và đáp ứng yêu cầu của client. Nhược điểm, nếu số lượng người dùng lớn, không gian lưu trữ session ở server có thể khiến server bị chậm.  
	- Stateless: Người dùng đăng nhập, server xác nhận và gửi phản hồi với một token, khi người dùng gửi request, server xác thực token bằng cách tính toán các giá trị nào đó, so sánh với token rồi đáp ứng request của client. Nhược điểm, token bị đánh cắp rất nguy hiểm.  
### Cacheable  
Response từ server cần chỉ rõ bản thân có thể cache hay không.  
### Hệ thống phân tầng  
Cho phép kiến trúc tạo nên từ các tầng phân cấp bằng cách ràng buộc hành vi của các component, các component này không thể truy cập xa hơn tầng liên kết trực tiếp.  
### Code on demand(optional)  
Cho phép client mở rộng bằng cách tải xuống và thực thư mã nguồn.  

## Tài nguyên của REST  
Dữ liệu, tệp,....  
Trạng thái tài nguyên hay đại diện tài nguyên bao gồm:  
	- Dữ liệu  
	- Siêu dữ liệu mô tả dữ liệu  
	- Liên kết siêu phương tiện cho phép client chuyển qua trạng thái tiếp theo.  
### Định danh tài nguyên  
Sử dụng định danh tài nguyên xác định loại tài nguyên tham gia.  
### Siêu phương tiện  
Định dạng dữ liệu của một đại diện là một kiểu phương tiện.  
Kiểu phương tiện cho biết cách một đại diện xử lý như nào.  
Ví dụ như đối tượng JSON student {name, class} đại diện cho trạng thái của một đối tượng thuộc lớp Student, JSON {name, class} là một kiểu phương tiện.  
### Tự mô tả  
Client không cần biết tài nguyên đó là gì, chỉ cần dựa theo kiểu phương tiện mà xử lý.  

## Phương thức tài nguyên  
Phương thức tài nguyên được dùng để thực hiện chuyển đổi mong muốn giữa hai trạng thái của tài nguyên bất kỳ.  
REST API không nhất thiết phải bám chặt vào các phương thức HTTP (GET/POST/PUT/DELETE), không có nghĩa là không nên làm vậy.  

## Phát triển API  
API là một component trừu tượng có tính tái sử dụng, cho biết hành vi mà không để lộ cách hoạt động bên trong.  
### API Specification  
Mô tả API cần:  
- Chỉ rõ hoạt động nghiệp vụ của API  
- API URL  
- Giao thức HTTP và phương thức  
- Cấu trúc request và từng trường trong request  
- Cấu trúc response và từng trường trong response  
- Các ràng buộc của giá trị trong các trường của request  
- Các cơ chế lấp đầy và sắp xếp dữ liệu  
- Thông tin authentication/authorization  
- Những mã thành công và báo lỗi  
- Bất cứ thông tin nào cần thiết có liên quan  
### API Security  
Chỉ có người dùng được xác thực quyền với chứng chỉ bảo mật được truy cập API.  
### Audit Logging  
Ghi lại các thông tin quan trọng liên qua tới việc sử dụng API.  
Phải chỉ ra được các trường hợp dùng sai mục đích hay truy cập không được xác thực quyền.  
### Performance  
Hiệu năng với API rất quan trọng. Không ứng dụng nào nên block người dùng trong khi request đang được xử lý trên server.  
