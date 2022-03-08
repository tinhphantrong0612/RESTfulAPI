# Content Negotiation  
Thông thường, tài nguyên REST có thể có nhiều đại diện, phần lớn bởi nhiều client khác nhau yêu cầu các đại diện khác nhau. Việc hỏi một đại diện thích hợp bởi client gọi là đàm phán nội dung.  
# Server-driven Vs Agent-driven Content Negotiation  
*Server-driven negotiation* là việc chọn đại diện phù hợp nhất bởi server.  
*Agent-driven negotitation* là việc chọn đại diện phù hợp nhất bởi client.  
Thực tế, không dùng server-driven negotitation.  
REST API phần lớn dựa trên agent-driven negotiation với **HTTP request headers** hoặc **resource URI patterns.**  
## Sử dụng HTTP Headers  
Client gửi request với header `Content-type` cho biết loại gói tin được gửi tới server, và sử dụng header `Accept` nhằm cho server biết loại nội dung muốn nhận.  
Trong header `Accept`, client có thể chỉ rõ loại content được ưu tiên bằng tham số `q`.  
Là cách phổ biến nhất và khuyến khích sử dụng.  
## Sử dụng URL Patterns  
Client có thể chỉ rõ phần mở rộng của URI, tuy nhiên sẽ phá vỡ tính nhất quán khi áp dụng chỉ dẫn đặt tên.  
