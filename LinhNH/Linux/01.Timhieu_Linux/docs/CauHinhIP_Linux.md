# Cấu hình địa chỉ IP trên hệ điều hành Ubuntu
### Cài đặt địa chỉ IP cho ubuntu sử dụng Netplan

- Dựa vào Virtual Network Editor để cấu hình địa chỉ IP

![hinhanh4](/LinhNH/Linux/01.Timhieu_Linux/images/ip-host.png)  

- Dùng câu lệnh để chỉnh sửa trên terminal

       linhnh@linhnh: ~$ sudo -i
       root@linhnh:~# nano /etc/netplan/00-installer-config.yaml
- Cấu hình như bên dưới 

![hinhanh4](/LinhNH/Linux/01.Timhieu_Linux/images/cauhinh1.png)  

- Sau khi gõ xong, nhấn Ctrl + X để thoát và lưu file.

_Chú ý: Cần xác định đúng tên interface và các thông số về IP của bạn._

Reboot hệ thống để IP được nhận

### Kiểm tra kết nối mạng
- Kiểm tra lại IP đã đặt ở trên 
![hinhanh4](/LinhNH/Linux/01.Timhieu_Linux/images/ip-may-ao.png)  


- Ping tới server google bằng câu lệnh

        ping 8.8.8.8

- Kết quả 
![hinhanh4](/LinhNH/Linux/01.Timhieu_Linux/images/ping.png)  
