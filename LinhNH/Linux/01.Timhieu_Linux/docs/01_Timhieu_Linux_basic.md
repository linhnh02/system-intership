# Tìm hiểu sơ lược về LINUX

## Mục lục
1. [Khái niệm về Linux](#1-khái-niệm-về-linux)  
2. [Cấu trúc thư mục của Linux](#2-cấu-trúc-thư-mục-của-linux)  
3. [Ưu điểm, hạn chế của Linux](#3-ưu-nhược-điểm-của-linux)  
    3.1 [Ưu điểm](#31-ưu-điểm)  
    3.2 [Nhược điểm](#32-nhược-điểm)
4. [Tìm hiểu Linux Command ](#4-linux-command-là-gì)
5. [Các loại user trong linux](#5-các-loại-user-trong-linux)
6. [Tìm hiểu Distro Linux ](#6-tìm-hiểu-về-distro-linux)  
    6.1 [Khái niệm Distro Linux](#61-distro-linux-là-gì)    
    6.2 [Phân loại Distro Linux](#62-phân-loại-các-distro-linux)


## 1. Khái niệm về Linux
![anh1](/LinhNH/Linux/01.Timhieu_Linux/images/linux.png)  

Linux là một hệ điều hành mã nguồn mở phổ biến, được phát triển bởi một cộng đồng toàn cầu các nhà phát triển và người dùng. Điều đặc biệt về Linux là tính mã nguồn mở cho phép bất kỳ ai cũng có thể xem, sửa đổi và phân phối mã nguồn của hệ điều hành này.

## 2. Cấu trúc thư mục của Linux
![anh2](/LinhNH/Linux/01.Timhieu_Linux/images/cautruc_ThuMuc.png)  

1. / – Root – Thư mục gốc
- Mỗi tập tin đơn và thư mục được bắt đầu thư mục gốc.
- Chỉ người dùng root mới có quyền ghi trong thư mục này.
- Lưu ý: rằng thư mục /root là thư mục của người dùng root chứ không phải là thư mục /.

2. /bin – Các tập tin thực thi của người dùng
- Chứa các tập tin thực thi.
- Các lệnh thường dùng của Linux mà bạn cần để dùng trong chế độ người dùng đơn được lưu ở đây.
- Các lệnh được sử dụng bởi tất cả người dùng trong hệ thống được lưu ở đây.
- Ví dụ: ps, ls, ping, grep, cp.

3. /sbin – Các tập tin thực thi của hệ thống
- Giống như /bin, /sbin cũng chứa các tập tin thực thi.
- Nhưng, các lệnh được lưu trong thư mục này về cơ bản được dùng cho người quản trị và được dùng để bảo trì hệ thống.
- Ví dụ: iptables, reboot, fdisk, ifconfig, swapon

4. /etc – Các tập tin cấu hình
- Chứa các tập tin cấu hình cần thiết cho tất cả các chương trình.
- Nó cũng chứa các đoạn mã khởi động và tắt mà được dùng để khởi động/dừng các chương trình đơn lẻ.
- Ví dụ: /etc/resolv.conf, /etc/logrotate.conf

5. /dev – Các tập tin thiết bị
- Chứa các tập tin thiết bị.
- Nó chứa các tập tin thiết bị đầu cuối như là USB hay bất kỳ thiết bị nào gắn vào hệ thống.
- Ví dụ: /dev/tty1, /dev/usbmon0

6. /proc – Thông tin tiến trình
- Chứa thông tin về các tiến trình của hệ thống.
- Như các tập tin chứa thông tin về các tiến trình đang chạy. Ví dụ: /proc/{pid} directory >>> lưu thông tin về tiến trình với pid bạn chọn.
- Hay các tập tin hệ thống ảo với nội dung về tài nguyên hệ thống. Ví dụ: /proc/uptime

7. /var – Các tập tin biến đổi
- var là viết tắt của các tập tin biến đổi.
- Gồm những tập tin mà dung lượng lớn dần theo thời gian sử dụng.
- Chẳng hạn — các tập tin ghi chú hệ thống (/var/log); các gói và các tập tin cơ sở dữ liệu (/var/lib); thư điện tử (/var/mail); hàng đợi – in queues (/var/spool); các tập tin khóa (/var/lock); các tập tin tạm được dùng khi khởi động lại (/var/tmp).

8. /tmp – Thư mục chứa các tập tin tạm
- Thư mục chứa các tập tin tạm được tạo bởi hệ thống và người dùng.
- Các tập tin trong thư mục này bị xóa khi hệ thống khởi động lại.

9. /usr – Các chương trình của người dùng
- Tập trung các tập tin thực thi, thư viện, tài liệu, và mã nguồn cho các chương trình mức độ thứ hai.
- /usr/bin chứa các tập tin thực thi cho các chương trình của người dùng. Nếu bạn không thể tìm thấy trong thư mục /bin thì tìm trong /usr/bin. Ví dụ: at, awk, cc, less, scp
- /usr/sbin chứa các tập tin thực thi cho quản trị hệ thống. Nếu bạn không thể tìm thấy trong /sbin thì tìm trong /usr/sbin. Ví dụ: atd, cron, sshd, useradd, userdel
- /usr/lib chứa các tập tin thư viện /usr/bin và /usr/sbin
- /usr/local chứa các chương trình của người dùng mà bạn cài từ mã nguồn. Ví dụ, khi bạn cài Apache từ mã nguồn, nó được đưa vào thư mục /usr/local/apache2

10. /home – Thư mục người dùng
- Chứa các tập tin của các người dùng trong hệ thống.
- Ví dụ: /home/john, /home/nikita

11. /boot – Các tập tin của chương trình khởi động máy
- Chứa những tập tin liên quan tới chương trình quản lý khởi động máy.
- Các tập tin initrd, vmlinux, grub được lưu trong thư mục /boot
- Ví dụ: initrd.img-2.6.32-24-generic, vmlinuz-2.6.32-24-generic

12. /lib – Các tập tin thư viện của hệ thống
- Chứa các tập tin thư viện để hỗ trợ các tập tin thực thi được lưu trong /bin và /sbin
- Tên của các tập tin này là ld* hay lib*.so.*
- Ví dụ: ld-2.11.1.so, libncurses.so.5.7

13. /opt – Các ứng dụng tùy chọn hay thêm
opt là viết tắt của optional.
- Chứa các ứng dụng thêm của các hãng khác nhau.
- Các ứng dụng thêm nên được cài trong thư mục con của thư mục /opt/.

14. /mnt – Thư mục Mount
- Thư mục mount tạm thời nơi mà người quản trị hệ thống có thể mount các tập tin hệ thống. 

15. /media – Các thiết bị tháo lắp
- Thư mục chưa các mount tạm thời cho các thiết bị tháo lắp.
- Ví dụ: /medica/cdrom cho CD-ROM; /media/floppy cho ổ đĩa mềm; /media/cdrecorder cho ổ đĩa ghi CD.

16. /srv – Dữ liệu dịch vụ
- srv là viết tắt của service.
- Chứa dữ liệu liên quan tới các dịch vụ trên máy chủ.
- Ví dụ: /srv/cvs chứa dữ liệu liên quan tới CVS.



## 3. Ưu, nhược điểm của Linux

### 3.1 Ưu điểm
- ___Tính miễn phí___: Mã nguồn mở hoàn toàn miễn phí, người dùng có thể tùy biến mọi câu code trong hệ điều hành theo ý của mình mà không sợ vi phạm bản quyền hay bị phạt như Window.
- ___Lựa chọn tốt nhất cho lập trình viên___: Hệ điều hành Linux hỗ trợ cực tốt cho những người làm công việc lập trình, quản trị hệ thống. Đó là bởi tính ổn định và hiệu năng cực cao mà Linux mang lại cho người dùng.

- ___Tính bảo mật và an toàn cao___: Nếu như với Window, virus sẽ khiến cho hệ điều hành này trở nên vất vả để chống đỡ. Thì với Linux, virus sẽ không thể hoạt động ổn định trên hệ điều hành này. Bạn chỉ cần xóa bỏ nó trong những câu lệnh nếu thấy chúng xuất hiện.

- ___Tính linh hoạt và phong phú___: Do là mã nguồn mở, cho nên người sử dụng có thể chỉnh sửa dễ dàng trên hệ thống theo đúng ý thích của mình. Vậy nên Linux sẽ không hạn chế sự sáng tạo và tưởng tượng của người sử dụng để họ có thể tha hồ lựa chọn ý tưởng để thực hiện.

### 3.2 Nhược điểm
- Linux chưa phổ biến nên chưa được các nhà sản xuất máy tính khai thác.
- Phần mềm hỗ trợ còn hạn chế.
- Một số nhà sản xuất không có Driver hỗ trợ hệ điều hành Linux.

## 4. Linux Command là gì?

Linux command là các lệnh được nhập vào terminal hoặc console để thực hiện các tác vụ trong Linux. Một số lệnh cơ bản trong Linux:

- ls: Liệt kê các file và thư mục trong thư mục hiện tại.
- cd: Di chuyển đến thư mục khác.
- pwd: Hiển thị đường dẫn đến thư mục hiện tại.
- mkdir: Tạo thư mục mới.
- rm: Xóa file hoặc thư mục.
- cp: Sao chép file hoặc thư mục.
- mv: Di chuyển hoặc đổi tên file hoặc thư mục.
- cat: Hiển thị nội dung của file.

## 5. Các loại user trong Linux

_Linux có ba loại user gồm:_

- Regular user: Đây là tài khoản user thông thường được tạo khi cài đặt Ubuntu các file được lưu trữ trong /home là thư mục chính của tài khoản này. Loại user này, không có quyền truy cập vào các thư mục của user khác.
- Root (Super user): Đây là tài khoản có quyền hạn cao nhất trong Linux. Loại user này có thể truy cập vào những file bị giới hạn quyền, cài đặt phần mềm và có quyền quản trị. Với tài khoản này, bạn có thể cài đặt phần mềm, thay đổi file hệ thống, hoặc thực hiện các tác vụ cần quyền quản trị bất kỳ lúc nào.
- User hệ thống : dùng để thực thi các module , script cần thiết phục vụ cho hệ điều hành.

## 6. Tìm hiểu về Distro Linux
### 6.1 Distro Linux là gì?
Distro Linux (Linux Distribution) là một bản phân phối của hệ điều hành Linux, bao gồm kernel Linux, shell và các ứng dụng cần thiết. Mỗi distro sẽ được cấu hình và tối ưu cho một mục đích cụ thể, chẳng hạn như máy chủ, máy tính cá nhân, máy tính xách tay, ... 
### 6.2 Phân loại các distro linux

Hiện tại, có khoảng 600 bản distro tồn tại, với gần 500 trong số đó phát triển tích cực, liên tục được sửa đổi và cải thiện. Bởi sự sẵn có của số lượng lớn phần mềm, distro khá là đa dạng về hình thức - phù hợp với từ desktop, server, laptop, netbooks, điện thoại di động, máy tính bảng cũng như môi trường tối thiếu thường để sử dụng trong các hệ thống nhúng.

- Một số loại distro phổ biến:
![hinhanh4](/LinhNH/Linux/01.Timhieu_Linux/images/ubuntu1.png)  

    - ___Ubuntu___ hiện tại đang làm một bản phân phối vô cùng hiện đại và được nhiều người dùng biết tới. Mục tiêu của nó đó chính là đem đến cho người dùng những trải nghiệm tốt nhất ngay trên máy chủ và máy tính. Hiện tại Ubuntu đã được cải tiến để phù hợp với tất cả yêu cầu của người dùng. Nhưng nó vẫn không làm mất đi những bản sắc riêng của bản thân. Ubuntu: là một trong những distro Linux phổ biến nhất, có giao diện đồ họa dễ sử dụng và cung cấp nhiều ứng dụng miễn phí.

    ![hinhanh4](/LinhNH/Linux/01.Timhieu_Linux/images/debian1.png)  

    - ___Debian___ đang là 1 hệ điều hành gồm có những phần mềm mã nguồn mở hoàn toàn miễn phí và hiện tại vẫn luôn được nhóm cộng đồng lập trình viên vô cùng yêu thích. Dù phát hành những phiên bản mới thường xuyên tuy nhiên Debian có một nhược điểm đó chính là cập nhật khá chậm so với những bản phân phối khác.
    
    ![hinhanh4](/LinhNH/Linux/01.Timhieu_Linux/images/fedora.png)  

    - ___Fedora___ đang là một phần mềm khá phổ biến và tập trung chủ yếu vào những phần mềm miễn phí vì vậy người dùng khi sử dụng thường xuyên gặp những khó khăn liên quan tới quá trình cài đặt những trình điều khiển về đồ họa độc quyền. Phiên bản này ở thời điểm hiện tại vẫn không ngừng được phát triển và cải tiến thêm.

    ![hinhanh4](/LinhNH/Linux/01.Timhieu_Linux/images/images.png)  

    - ___Red Hat Enterprise Linux___ (RHEL) đây là nền tảng thương mại phổ biến, có hai phiên bản là RHEL (hỗ trợ 2CPU) và RHELAP (không giới hạn CPU). Red Hat được sử dụng bởi các cơ quan, tổ chức. Red Hat và các distro dựa trên nó dùng chương trình quản lý gói có tên là RPM (Red Hat Package Management).

    ![hinhanh4](/LinhNH/Linux/01.Timhieu_Linux/images/centos.png)  

    - ___CentOS___ dựa theo Red Hat Enterprise Linux, dành cho ai muốn sử dụng Red Hat mà kông phải trả phí hỗ trợ để sử dụng nó. Nó cũng dùng trình quản lý gói RPM và các công cụ quản trị tương tự Red Hat.