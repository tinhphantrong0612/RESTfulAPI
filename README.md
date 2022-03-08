# REST (REpresentation State Transfer)  
Phong cách kiến trúc cho hệ thống phân phối [hypermedia](https://github.com/tinhphantrong0612/RESTfulAPI/blob/main/Hypermedia.md).  
Như các phong cách kiến trúc khác, REST cũng có những nguyên tắc và ràng buộc.  
Một Web API xây dựng theo phong cách REST gọi là *REST API*.  
## [Nguyên tắc của REST](https://github.com/tinhphantrong0612/RESTfulAPI/blob/main/ArchitecturalConstraint.md)  
### Uniform Constraint  
### Client-server  
### Stateless  
### [Cacheable](https://github.com/tinhphantrong0612/RESTfulAPI/blob/main/Caching.md)  
### Layered System   
### Code on demand(optional)  
## Phát triển API  
API là một component trừu tượng có tính tái sử dụng, cho biết hành vi mà không để lộ cách hoạt động bên trong.  
### API Specification  
Mô tả API cần:  
- Chỉ rõ hoạt động nghiệp vụ của API  
- [API URL](https://github.com/tinhphantrong0612/RESTfulAPI/blob/main/NamingGuide.md)  
- Giao thức HTTP và phương thức  
- Cấu trúc request và từng trường trong request  
- Cấu trúc response và từng trường trong response  
- Các ràng buộc của giá trị trong các trường của request  
- Các cơ chế lấp đầy và sắp xếp dữ liệu  
- Thông tin authentication/authorization  
- Những mã thành công và báo lỗi  
- Bất cứ thông tin nào cần thiết có liên quan  
### [API Security](https://github.com/tinhphantrong0612/RESTfulAPI/blob/main/Security.md)  
Chỉ có người dùng được xác thực quyền với chứng chỉ bảo mật được truy cập API.  
### Audit Logging  
Ghi lại các thông tin quan trọng liên qua tới việc sử dụng API.  
Phải chỉ ra được các trường hợp dùng sai mục đích hay truy cập không được xác thực quyền.  
### Performance  
Hiệu năng với API rất quan trọng. Không ứng dụng nào nên block người dùng trong khi request đang được xử lý trên server.  
