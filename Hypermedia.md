# Hypermedia  
Siêu phương tiện?  
Là nội dung chứa các thông tin cho phép liên kết tới các nội dụng khác.  
Ví dụ như thông tin một cuốn sách (Book) sẽ có một số ít thông tin về tác giả (Author), mà thông qua đó có thể tìm kiếm thông tin đầy đủ của tác giả.  
# HATEOAS (Hypermedia as the Engine of Application State)  
Client có thể yêu cầu một tài nguyên nào đó bằng cách sử dụng liên kết từ Hypermedia trong response của server. Tương tự như việc click vào hyperlink trên một trang web để đạt mục đích cuối.  
Nhờ vào đó, mà trạng thái của client sẽ được điều chỉnh thông qua Hypermedia trả về từ Server. Client không cần phải chỉ rõ liên kết cho phần lớn tài nguyên.  
