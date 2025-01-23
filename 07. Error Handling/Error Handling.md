# Xử lý Lỗi 


## Mô tả 
Lỗi thường được coi là vô hại vì chúng cung cấp dữ liệu chẩn đoán và thông báo có thể giúp người dùng hiểu được vấn đề đang gặp phải hoặc giúp nhà phát triển gỡ lỗi.

Bằng cách cố gắng gửi dữ liệu không mong muốn hoặc buộc hệ thống vào một số trường hợp và tình huống ngoại lệ nhất định, hệ thống hoặc ứng dụng sẽ thường xuyên tiết lộ một chút thông tin về những gì đang diễn ra bên trong, trừ khi nhà phát triển tắt mọi lỗi có thể xảy ra và trả về một thông báo tùy chỉnh nhất định.

Vì vậy xử lý lỗi là một phần của bảo mật tổng thể của ứng dụng.

Xử lý lỗi không đúng cách có thể cho phép kẻ tấn công:
- Hiểu các API đang được sử dụng nội bộ.
- Thu thập các phiên bản và loại ứng dụng đang được sử dụng.
- Tấn công từ chối dịch vụ (DoS) hoặc một ngoại lệ chưa được xử lý.
- Kẻ tấn công hiểu rõ hơn về hệ thống.

## Khuyến cáo 
- Quản lý các ngoại lệ theo [centralized manner](https://owasp.org/www-project-code-review-guide/#Centralised_exception_handling_.28Struts_Example.29) để tránh các khối try/catch trùng lặp trong mã. Đảm bảo rằng tất cả các hành vi không mong muốn được xử lý chính xác bên trong ứng dụng.
- Đảm bảo rằng thông báo lỗi hiển thị cho người dùng không làm rò rỉ dữ liệu quan trọng nhưng vẫn đủ chi tiết để người dùng có thể phản hồi phù hợp.
- Đảm bảo rằng các ngoại lệ được ghi lại theo cách cung cấp đủ thông tin để nhóm hỗ trợ, đảm bảo chất lượng, giám định hoặc ứng phó sự cố hiểu được vấn đề.
- Kiểm tra và xác minh code xử lý lỗi một cách cẩn thận.

## Tham khảo 
[Error Handling Cheat Sheet](https://cheatsheetseries.owasp.org/cheatsheets/Error_Handling_Cheat_Sheet.html)