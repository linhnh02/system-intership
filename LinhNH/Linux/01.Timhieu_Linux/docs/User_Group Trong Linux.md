# Tìm hiểu về User, Group trong Linux

Cả người dùng và nhóm đều đóng một vai trò rất lớn trong việc quản lý hệ thống Linux. Đây là thành phần quan trong của hệ thống Linux, duy trì tính bảo mật bằng cách cho phép quản trị viên gán quyền và ủy thác trách nhiệm một cách cẩn thận.

## Định nghĩa user

Users được định nghĩa trong một hệ thống để xác định “ai? được quyền dùng cái gì?” trong hệ thống đó.

Với Linux, mỗi user có một định danh duy nhất, gọi là UID (User ID).

- User ID từ 0 – 99: user có quyền quản trị.

- User ID >= 500: không phải user hệ thống mà là user thường do người quản trị tạo ra.

_Mỗi user thuộc ít nhất một group. Mỗi group cũng có một định danh duy nhất là GID._

Trong Linux có thể chỉnh sửa thông tin của users bằng công cụ, hoặc sửa trực tiếp bằng text file.

Những file định nghĩa thông tin users:
- /etc/passwd: chứa thông tin user login, password mã hóa, UID, GID, home directory và login shell. Mỗi dòng là thông tin của một user.
- /etc/shadow: chứa thông tin password mã hóa, thời gian sử dụng password, thời gian phải thay đổi password…
- /etc/group: chứa thông tin group.

## Cấu trúc file /etc/passwd
- Là file chứa thông tin về các tài khoản user trên máy. Mọi user đều có thể tập tin này nhưng chỉ có root mới có quyền thay đổi.

      # cat /etc/paswd

![anh](/LinhNH/Linux/01.Timhieu_Linux/images/etc_passwd.png)

Cấu trúc các trường thông tin: 
- Cột 1	Tên người sử dụng
- Cột 2	Mã liên quan đến mật khẩu cho Unix chuẩn và ‘x’ đối với Linux. Linux lưu mã này trong một tập tin khác /etc/shadow mà chỉ có root mới có quyền đọc
- Cột 3	User ID
- Cột 4	Group ID
- Cột 5	Tên mô tả người sử dụng (Comment)
- Cột 6	Thư mục home của user. Thường sẽ nằm trong /home/”tên_tài_khoản”
- Cột 7	Shell sẽ hoạt động sau khi user login, thường là /bin/bash

## Cấu trúc file /etc/shadow
Là tệp chứa các thông tin về mật khẩu đã được mã hóa của từng người dùng trên hệ thống dựa trên Linux. Bất cứ khi nào thêm người dùng mới vào hệ thống Linux, tệp /etc/shadow sẽ tự động sửa đổi để lưu trữ thông tin xác thực về người dùng. 

    # sudo cat /etc/shadow

![anh](/LinhNH/Linux/01.Timhieu_Linux/images/etc-shadow.png)


Cấu trúc các trường thông tin:
- Cột 1: Tên người dùng
- Cột 2: Mật khẩu: có định dạng kiểu $id$salt$hash  
  + id: xác định thuật toán mã hóa được sử dụng để mã hóa mật khẩu. Giá trị có thể là 1 (MD5), 2a (Blowfish), 2y (Eksblowfish), 5 (SHA-256) hoặc 6 (SHA - 512).
  + salt: mã hóa và xác thực mật khẩu
  + hash: mật khẩu của người dùng khi nó xuất hiện sau khi băm
- Cột 3: Ngày thay đổi mật khẩu cuối cùng
- Cột 4: Tuổi mật khẩu tối thiểu: số ngày mà người dùng phải đợi sau khi thay đổi mật khẩu của họ trước khi thay đổi lại
- Cột 5: Tuổi mật khẩu tối đa
- Cột 6: Thời gian cảnh báo: xác định số ngày trước khi mật khẩu đạt đến tuổi tối đa .
- Cột 7: Thời gian không hoạt động: số ngày có thể trôi qua sau khi mật khẩu của người dùng đạt đến tuổi tối đa trước khi hệ thống vô hiệu hóa tài khoản.
- Cột 8: Ngày hết hạn: ngày kết thúc thời gian không hoạt động khi hệ thống sẽ tự động vô hiệu hóa tài khoản của người dùng.
- Cột 9: Unuse (không sử dụng): hiện không phục vụ mục đích nào và được dành để sử dụng trong tương lai


















-------------
## Group 
Group là tập hợp nhiều user lại.

Mỗi user luôn là thành viên của một group.

Khi tạo một user thì mặc định một group được tạo ra.

Mỗi group còn có một định danh riêng gọi là GID.

Định danh của group thường sử dụng giá trị bắt đầu từ 500.
- Mỗi users cần có những thông tin: tên user, UID, tên group, GID, home directory. Windows quản lý thông tin bằng LDAP, Kerberos. Linux quản lý thông tin bằng file text.



## Cấu trúc file /etc/group

    # nano etc/group

![anh](/LinhNH/Linux/01.Timhieu_Linux/images/etc-group.png)


Là tập tin văn bản chứa thông tin về nhóm user trên máy. Mọi user đều có thể đọc tập tin này nhưng chỉ có root mới có quyền thay đổi. Mỗi dòng trong tập tin chứa thông tin về các nhóm user trên máy, định dạng của dòng gồm nhiều cột giá trị, dấu “:” được sử dụng để phân cách các cột. 
- Cột 1: Tên nhóm
- Cột 2: Mật khẩu (đã được mã hóa)
- Cột 3: Mã nhóm (GID)
- Cột 4: Danh sách các user thuộc cùng nhóm
