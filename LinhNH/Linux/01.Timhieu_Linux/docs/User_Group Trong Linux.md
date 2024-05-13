# Tìm hiểu về User, Group trong Linux

__Định nghĩa user__

Users được định nghĩa trong một hệ thống để xác định “ai? được quyền dùng cái gì?” trong hệ thống đó.

Với Linux, mỗi user có một định danh duy nhất, gọi là UID (User ID).

- User ID từ 0 – 99: user có quyền quản trị.

- User ID >= 500: không phải user hệ thống mà là user thường do người quản trị tạo ra.

_Mỗi user thuộc ít nhất một group. Mỗi group cũng có một định danh duy nhất là GID._

Group là tập hợp nhiều user lại.

Mỗi user luôn là thành viên của một group.

Khi tạo một user thì mặc định một group được tạo ra.

Mỗi group còn có một định danh riêng gọi là GID.

Định danh của group thường sử dụng giá trị bắt đầu từ 500.
- Mỗi users cần có những thông tin: tên user, UID, tên group, GID, home directory. Windows quản lý thông tin bằng LDAP, Kerberos. Linux quản lý thông tin bằng file text.

Trong Linux có thể chỉnh sửa thông tin của users bằng công cụ, hoặc sửa trực tiếp bằng text file.

Những file định nghĩa thông tin users:
- /etc/passwd: chứa thông tin user login, password mã hóa, UID, GID, home directory và login shell. Mỗi dòng là thông tin của một user.
- /etc/shadow: chứa thông tin password mã hóa, thời gian sử dụng password, thời gian phải thay đổi password…
- /etc/group: chứa thông tin group.

Cấu trúc file /etc/passwd
------------
Cấp quyền cho user và group
Ta dùng lệnh chmod

Để có quyền đọc viết hoặc chỉnh sửa một file thì mỗi user cần được user root cấp quyền cho mới có thể thự thi được

Quyền đọc: r = 4

Quyền Viết: w = 2

Quyền thực thi: x = 1

Kí tự - đầu tiên là một cờ đặc biệt để chỉ loại file, - với file thông thường, d với thư mục, c với thiết bị, l với liên kết (liên kết tới một file khác).

o+rws: cho phép user sở hữu có full quyền

g+rw: cho phép group sở hữu có quyền đọc và ghi

u+w: cho phép các user còn lại có quyền đọc

a+rws: cho phép toàn bộ user có full quyền (777)