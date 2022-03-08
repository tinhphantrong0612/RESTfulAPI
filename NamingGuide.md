# Naming Guide  
## 1. Tài nguyên  
Trong REST, đại diện cho dữ liệu nguyên bản là **tài nguyên**. Tài nguyên nên có một quy tắc đặt tên phù hợp và rõ ràng.  
Tài nguyên có thể là một singleton, collection, hoặc sub-collection chứa các tài nguyên khác.  
REST API sử dụng Uniform Resource Identifier (URI) để xác định tài nguyên. URI cần phải cụ thể và chỉ rõ được thông tin về tài nguyên.  
## 2. Thực hành  
### 2.1. Sử dụng danh từ đại diện cho tài nguyên  
RESTful URI nên định danh tài nguyên như một thứ gì đó (danh từ) thay vì một hành động (động từ), áp dụng tương tự với các thuộc tính của tài nguyên.  
Chia **resource archetypes** thành bốn mục (document, collection, store, và controller), và **cố đưa tài nguyên vào 4 mục này, đặt tên theo quy định**.  
*Tránh việc lai tạo giữa nhiều archetype.*  
#### 2.1.1. document  
Tài nguyên document là một khái niệm đơn lẻ, tương tự như một đối tượng hay một bản ghi cơ sở dữ liệu.  
Trong REST, có thể coi đó là một tài nguyên trong bộ các tài nguyên.  
Đặt tên số ít.  
#### 2.1.2. collection  
Một tập các tài nguyên do do server quản lý.  
Client có thể yêu cầu thêm tài nguyên, nhưng vẫn phải do server quyết định có thêm hay không.  
Đặt tên số nhiều.  
#### 2.1.3. store  
Tập các tài nguyên do client quản lý.  
Client có thể thêm mới, tải xuống, xóa chúng.  
Một store không tạo URI mới, thay vào đó, mỗi tài nguyên được lưu có một URI do client chọn khi đưa vào store.  
Đặt tên số nhiều.  
#### 2.1.4. controller  
Một tài nguyên controller định hình một khái niệm thủ tục.  
Tài nguyên controller giống như một hàm, với các tham số, giá trị trả về.  
Sử dụng động từ để đặt tên.  
### 2.2. Đảm bảo nhất quán  
- Sử dụng (/) cho biết quan hệ phân cấp  
- Bỏ đuôi (/) ở cuối URI
- Sử dụng (-) cho URI, phân tách từ  
- Không dùng dấu gạch dưới (_)  
- Không viết hoa  
- Không dùng phần mở rộng của file, thay vào đó, dùng `Content-type` trong header  
- Không dùng CRUD trong URI, chỉ dùng URI để phân biệt các tài nguyên, không dùng xác định phương thức  
- Dùng query để lọc từ URI  
