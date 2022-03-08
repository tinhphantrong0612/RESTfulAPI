# Caching  
Caching là khả năng lưu lại một đại diện tài nguyên nào đó trên đường đi của request-response.  
Đường đi của một request:  
	- Đi qua một hoặc một loạt cache (local cache, proxy cache, hoặc reverse proxy), nếu một trong các cache có một bản sao của đại diện tài nguyên, thì nó sẽ được dùng để đáp ứng yêu cầu.  
	- Nếu không có cache, request đi tiếp tới server gốc để yêu cầu tài nguyên, khi đó server sẽ xử lý request.    
Server phản hồi request bằng một response. Đường đi của response:  
	- Server tạo response, quy định các HTTP headers, cho biết khả năng cache, ai được cache, và cache trong bao lâu.  
	- Qua mỗi cache, response có thể được sao chép và lưu lại nếu caching metadata cho phép.    
Caching cải thiện chất lượng dịch vụ bằng cách:  
	- Giảm băng thông  
	- Giảm độ trễ  
	- Giảm tải server  
	- Ẩn lỗi mạng  
# Caching trong REST API  
Là một ràng buộc kiến trúc của REST.  
	- `GET` request nên cacheable mặc định. Thông thường, trình duyệt coi tất cả GET request là cacheable.  
	- `POST` request không cacheable mặc định, nhưng có thể sửa bằng header với `Expires` hoặc `Cache-Control`, được thêm vào response.  
	- `PUT` và `DELETE` không được cache.    
HTTP dates luôn là GMT, không phải local time.  
# Cache Control Header: `Expires`, `Cache-Control`, `ETag`, `Last-Modified`  
