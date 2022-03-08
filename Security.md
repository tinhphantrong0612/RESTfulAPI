# REST API Security Essentials  
REST API stateless, nên mỗi API request cần có một thứ gì đó đi kèm để xác thực danh tính và quyền.  
## Các nguyên tắc thiết kế bảo mật không chỉ của REST  
- Least Privilege: Mỗi thực thể chỉ nên có một số quyền để thực hiện các hành động đã được xác thực quyền. Quyền có thể được cấp và thu hồi khi không còn sử dụng.  
- Fail-Safe default: Mọi truy cập tới tài nguyên cần phải bị từ chối nếu không được cấp quyền cụ thể.  
- The economy of Mechanism: Thiết kế đơn giản nhất có thể. Các giao diện của component và tương tác giữa chúng nên đủ đơn giản để hiểu.  
- Complete Mediation: Một hệ thống nên validate quyền truy cập tới mọi tài nguyên để đảm bảo các truy cập đó được cho phép và không nên phụ thuộc vào các ma trận quyền được thiết lập trước đó, do nếu quyền bị thu hồi mà ma trận quyền không được cập nhật, sẽ dẫn tới vi phạm.  
- Open Design: Xây dựng một hệ thống mở, không có thuật toán bí mật, chỉ có khóa bí mật.  
- Seperation of Privilege: Cấp quyền cho một thực thể không nên dựa trên một điều kiện, tổng hợp các điều kiện dựa trên loại tài nguyên thì tốt hơn.  
- Least Common Mechanism: Tránh việc chia sẻ trạng thái giữa các component. Nếu ai đó phá hỏng trạng thái được chia sẻ, các component dựa trên đó sẽ hỏng.  
- Psychological Acceptability: Các cơ chế bảo mật không được làm tài nguyên khó truy cập hơn nhiều so với khi không có cơ chế bảo mật. Đồng nghĩa, bảo mật không khiến trải nghiệm người dùng tệ hơn.  
## Ứng dụng bảo mật REST API  
### KISS: Càng đơn giản càng tốt  
### Dùng HTTPS  
### Băm mật khẩu  
### Không lưu thông tin trên URL: Tránh dùng query với các thông tin quan trọng, nên đưa vào gói tin `POST`  
### Sử dụng OAuth  
### Xem xét thêm vào mốc thời gian, tránh tấn công phát lại  
### Validate các tham số do người dùng nhập: Server quan trọng hơn, nhưng vẫn nên cả ở client, hạn chế nhiều request nhất có thể  
