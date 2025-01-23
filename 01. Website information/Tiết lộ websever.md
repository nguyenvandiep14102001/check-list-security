# Thông tin webserver

## Kiểm tra
Không nên tiết lộ phiên bản và loại máy chủ đang chạy thông qua header ***server***  trong response

Ví dụ, đây là phản hồi cho một yêu cầu được gửi tới máy chủ Apache.
```HTTP/1.1 200 OK
Date: Thu, 05 Sep 2024 17:42:39 GMT
Server: Apache/2.4.41 (Unix)
Last-Modified: Thu, 05 Sep 2024 17:40:42 GMT
ETag: "75-591d1d21b6167"
Accept-Ranges: bytes
Content-Length: 117
Connection: close
Content-Type: text/html
...
```
Đây là một phản hồi khác, lần này được gửi bởi nginx.
```
HTTP/1.1 200 OK
Server: nginx/1.17.3
Date: Thu, 05 Sep 2019 17:50:24 GMT
Content-Type: text/html
Content-Length: 117
Last-Modified: Thu, 05 Sep 2019 17:40:42 GMT
Connection: close
ETag: "5d71489a-75"
Accept-Ranges: bytes
...
```
## Tác động
Kẻ tấn công có thể dựa vào đó để nghiên cứu các lỗ hổng đã biết trước của các phiên bản đang chạy.

## Yêu cầu

Mặc dù thông tin máy chủ bị lộ không nhất thiết là một lỗ hổng, nhưng đó là thông tin có thể hỗ trợ kẻ tấn công khai thác các lỗ hổng khác có thể tồn tại. Thông tin máy chủ bị lộ cũng có thể khiến kẻ tấn công tìm thấy các lỗ hổng máy chủ cụ thể theo phiên bản có thể được sử dụng để khai thác các máy chủ chưa vá. Vì lý do này, nên thực hiện một số biện pháp phòng ngừa :

- Che giấu thông tin máy chủ web trong các header.
- Đảm bảo máy chủ web luôn được cập nhật phần mềm và bản vá mới nhất.