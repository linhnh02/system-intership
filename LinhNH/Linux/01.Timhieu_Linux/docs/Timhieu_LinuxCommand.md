# Tìm hiểu 1 số lệnh cơ bản trong Linux
## 1. Lệnh cd (change directory)
Dùng để chuyển vị trí làm việc sang thư mục khác .

    # cd [path]

- **`cd root/snap/`** : Chuyển đến thư mục /snap (đường dẫn tuyệt đối)
- **`cd check1`** : Chuyển đến thư mục check1 là thư mục con của thư mục hiện hành (đường dẫn tương đối)
- **`cd ..`** : Chuyển đến thư mục cha
- **`cd`** = **`cd ~`** : Chuyển đến thư mục home của user hiện tại
- **`cd -`** : Chuyển đến thư mục mình vừa rời đi trước đó

![anh](/LinhNH/Linux/01.Timhieu_Linux/images/change_directory.png)  


## 2. Lệnh ls (list)

    # ls [options] [path]

2.1 **`ls`** : Hiển thị danh sách các thư mục và tệp tin  
2.2 **`ls -1`** : Hiển thị mỗi mục trên 1 dòng  
2.3 **`ls -t`** : Hiển thị theo thời gian chỉnh sửa   
2.4 **`ls -t | head -sốfile`**: Hiển thị các file được chỉnh sửa cuối cùng

![anh](/LinhNH/Linux/01.Timhieu_Linux/images/list.png)  

2.5 **`ls -l`** : Hiển thị chi tiết thông tin các file, thư mục

![anh](/LinhNH/Linux/01.Timhieu_Linux/images/ls-l.png)  

Trong đó:
- Kí tự đầu tiên để  định dạng:  
    `-` : file bình thường  
    `d` : thư mục  
    `s` : file socket  
    `l` : link file  

- Trường 1: File permission  
- Trường 2: Số lượng liên kết đến tệp hay thư mục đó
- Trường 3: Chủ sở hữu của tệp, thư mục
- Trường 4: Nhóm của tệp, thư mục
- Trường 5: Kích thước của tệp, thư mục đó (đơn vị: byte)
- Trường 6: Thời gian sửa đổi cuối cùng
- Trường 7: Tên của tệp, thư mục

2.6 **`ls -a`** : Hiển thị các file ẩn  
_Trong Linux, các file có tên bắt đầu bằng dấu chấm được coi là file ẩn và nó không hiển thị cùng các file bình thường._ 

![anh](/LinhNH/Linux/01.Timhieu_Linux/images/ls-a.png)  

2.7 **`ls -l -a`** = **`ls -la`** : Hiển thị chi tiết các thông tin, bao gồm cả các file bị ẩn

![anh](/LinhNH/Linux/01.Timhieu_Linux/images/ls-la.png)  

2.8 Hiển thị danh sách để lấy ra tên file, thư mục cách nhau bằng dấu , và ""
- **`ls 1m`**
- **`ls 1mQ`**

2.9 Liệt kê những file có tên file theo mong muốn

Ví dụ tìm những file có kí tự chứa __check__

- **`ls -l check*`**

![anh](/LinhNH/Linux/01.Timhieu_Linux/images/search-file.png)  

2.10 **`ls -lh`** : Hiển thị kích thước của các tập tin, thư mục ở dạng dễ đọc (M - MB, K - KB, G - GB)

![anh](/LinhNH/Linux/01.Timhieu_Linux/images/ls-lh.png)  

## 3. Lệnh pwd (print working directory)
_Hiển thị đường dẫn của thư mục đang làm việc_

    pwd [option]

Các tùy chọn được sử dụng với pwd:


**`-L`** (logical)
 Sử dụng PWD từ môi trường, ngay cả khi nó chứa các liên kết tượng trưng

**`-P`** (physical)
 Tránh tất cả các liên kết tượng trưng

**`–help`**
 Hiển thị trợ giúp này và thoát

**`–version`**
 Thông tin phiên bản đầu ra và thoát

![anh](/LinhNH/Linux/01.Timhieu_Linux/images/pwd.png)  

## 4. Lệnh mkdir (make directory)
_Tạo thư mục_
  
    # mkdir [Tùy chọn] Tên_thư_mục

![anh](/LinhNH/Linux/01.Timhieu_Linux/images/mkdir.png)
   