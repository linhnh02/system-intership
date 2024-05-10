# Tìm hiểu về VM Ware Workstation

# Mục lục

## 1. Cài đặt VM Ware Workstation

B1: Truy cập vào đây để tải file cài đặt về máy

B2: Nhấn đúp chuột vào file vừa tải để bắt đầu cài đặt

B3: Chọn Next để tiếp tục cài đặt

B4: Đánh dấu tick vào mục I accept the terms in the License Agreement -> chọn Next

B5: 

## 2. Tạo máy ảo trên VMware

### 2.1 CentOS-7 Minimal

### 2.2 Ubuntu Server 22.04

## 3. Phân biệt 3 chế độ network
VM Ware cũng sẽ cps Virtual Switch để kết nối nhiều thiết bị trong cùng đường mạng. Để kiểm tra VMware Switch, bạn vào Edit rồi chọn Virtual Network. Thông thường ở đây sẽ có 3 con hàng được dựng sẵn như bên dưới:

![anh](/LinhNH/Linux/02.Timhieu_VMWare_Workstation/images/3mode.png)  

### 3.1 NAT
Chế độ NAT: ở chế độ này, card mạng của máy ảo kết nối với VMnet8, VNnet8 cho phép máy ảo đi ra mạng vật lý bên ngoài internet thông qua cơ chế NAT (NAT device). Lúc này lớp mạng bên trong máy ảo khác hoàn toàn với lớp mạng của card vật lý bên ngoài, hai mạng hoàn toàn tách biệt. IP của card mạng máy ảo sẽ được cấp bởi DHCP của VMnet8, trong trường hợp bạn muốn thiết lập IP tĩnh cho card mạng máy ảo bạn phải đảm bảo chung lớp mạng với VNnet8 thì máy ảo mới có thể đi internet.

![anh](/LinhNH/Linux/02.Timhieu_VMWare_Workstation/images/NAT.png)  

- Card NAT chỉ có thể giao tiếp với card mạng ảo VMnet8 trên máy thật.
- Card NAT chỉ có thể giao tiếp với các card NAT trên các máy ảo khác.
- Card NAT không thể giao tiếp với mạng vật lý mà máy tính thật đang kết nối. Tuy nhiên nhờ cơ chế NAT được tích hợp trong VMWare, máy tính ảo có thể gián tiếp liên lạc với mạng vật lý bên ngoài.

### 3.2 Bridge
Chế độ Bridge: ở chế độ này, card mạng trên máy ảo được gắn vào VMnet0, VMnet0 này liên kết trực tiếp với card mạng vật lý trên máy thật, máy ảo lúc này sẽ kết nối internet thông qua card mạng vật lý và có chung lớp mạng với card mạng vật lý.

![anh](/LinhNH/Linux/02.Timhieu_VMWare_Workstation/images/Bridge.png)  

- Card Bridge trên máy ảo chỉ có thể giao tiếp với card mạng - thật trên máy thật.
- Card mạng Bridge này có thể giao tiếp với mạng vật lý mà máy tính thật đang kết nối.

### 3.3 Host-only
Cơ chế Host-only: máy ảo được kết nối với VMnet có tính năng Host-only, trong trường hợp này là VMnet1 . VMnet Host-only kết nối với một card mạng ảo tương ứng ngoài máy thật (như đã nói ở phần trên). Ở chế độ này, các máy ảo không có kết nối vào mạng vật lý bên ngoài hay internet thông qua máy thật , có nghĩa là mạng VMnet Host-only và mạng vật lý hoàn toàn tách biệt. IP của máy ảo được cấp bởi DHCP của VMnet tương ứng. Trong nhiều trường hợp đặc biệt cần cấu hình riêng, ta có thể tắt DHCP trên VMnet và cấu hình IP bằng tay cho máy ảo.

![anh](/LinhNH/Linux/02.Timhieu_VMWare_Workstation/images/host-only.png)  

- Card Host-only chỉ có thể giao tiếp với card mạng ảo VMnet1 trên máy thật.
- Card Host-only chỉ có thể giao tiếp với các card Host-only trên các máy ảo khác.
- Card Host-only không thể giao tiếp với mạng vật lý mà máy tính thật đang kết nối.  

## 4. Sử dụng chế độ mạng NAT cho các máy ảo để truy cập internet

## 5. Sử dụng chế độ card Host-only để 2 máy ảo kết nối với nhau

- Tạo 2 máy ảo khác nhau trên VMware 
- Thực hiện kết nối mạng giữa 2 máy
  - Kiểm tra ip máy ảo bằng câu lệnh: ip a

  Máy ảo 1

  ![anh](/LinhNH/Linux/02.Timhieu_VMWare_Workstation/images/ip1.png) 

  Máy ảo 2

  ![anh](/LinhNH/Linux/02.Timhieu_VMWare_Workstation/images/ip2.png) 

  Ping máy ảo 2 sang máy ảo 1

  ![anh](/LinhNH/Linux/02.Timhieu_VMWare_Workstation/images/ping2may.png)  


## 6. Sử dụng 1 card Bridge để từ máy ảo ping ra laptop cá nhân

- Vào chế độ Network Adapter để cài đặt chế độ mạng bridged
- Kiểm tra cấu hình của mính tính cá nhân

![anh](/LinhNH/Linux/02.Timhieu_VMWare_Workstation/images/ip-may.png)  

- Kiểm tra cấu hình của máy ảo

![anh](/LinhNH/Linux/02.Timhieu_VMWare_Workstation/images/ip-bridged.png)  

- Thực hiện ping giữa máy ảo sang máy tính cá nhân

![anh](/LinhNH/Linux/02.Timhieu_VMWare_Workstation/images/ping-bridged.png)  

