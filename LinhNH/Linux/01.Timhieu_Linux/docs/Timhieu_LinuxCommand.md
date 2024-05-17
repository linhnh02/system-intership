# Tìm hiểu 1 số lệnh cơ bản trong Linux

## 1. Lệnh cd (change directory)
Dùng để chuyển vị trí làm việc sang thư mục khác .

    # cd [path]

- **`cd root/snap/`** : Chuyển đến thư mục /snap (đường dẫn tuyệt đối)
- **`cd check1`** : Chuyển đến thư mục check1 là thư mục con của thư mục hiện hành (đường dẫn tương đối)
- **`cd ..`** : Chuyển đến thư mục cha
- **`cd`** = **`cd ~`** : Chuyển đến thư mục home của user hiện tại / quay lại thư mục trước

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
   
    # mkdir -v Tên_thư_mục 
    // Tạo thư mục và hiển thị thông báo tạo thự mục

![anh](/LinhNH/Linux/01.Timhieu_Linux/images/mkdir-v.png)


## 6. Lệnh rmdir (remove directory)
_Xóa thư mục_ (Chỉ cho phép xóa thư mục rỗng)

    # rmdir Tên_thư_mục

![anh](/LinhNH/Linux/01.Timhieu_Linux/images/rmdir.png)
   
## 7. Lệnh touch
_Tạo file mới trống thông qua dòng lệnh_

    # touch Tên_file

![anh](/LinhNH/Linux/01.Timhieu_Linux/images/touch.png)

## 8. Sao chép thư mục, tệp in 
### 8.1. Copy nội dung 1 file vào file khác
    # cp Tên_File_Nguồn Tên_Thư_Mục_Đích
    // Tên tệp sao chép và tệp muốn sao chép (source_file và target_file) phải khác nhau để không bị lưu đè

![anh](/LinhNH/Linux/01.Timhieu_Linux/images/cp.png)

### 8.2 Copy file vào thư mục khác
    # cp Tên_file Tên_thư_mục

![anh](/LinhNH/Linux/01.Timhieu_Linux/images/8.2.png)

### 8.3 Thông báo có muốn ghi đè nội dung tập tin hay không
    # cp -i test1.txt test2.txt
    -- i: inteactive (tương tác)
    // Sử dụng tùy chọn -i để nhận được thông báo xác nhận trước khi ghi đè các tệp.       

![anh](/LinhNH/Linux/01.Timhieu_Linux/images/copy-file.png)

### 8.4 Xem quá trình sao chép file
    # cp -v Filename1 Filename2
    // -v -verbose (xem quá trình)

![anh](/LinhNH/Linux/01.Timhieu_Linux/images/8.4.png)

## 9. Lệnh mv: di chuyển file và thư mục

    # mv [OPTIONS] SOURCE DESTINATION

Để di chuyển text1 từ thư mục làm việc hiện tại hiện tại sang thư mục /text2 thì bạn sẽ chạy lệnh sau: 
    # mv text1 / text2

Cú pháp để di chuyển thư mục cũng giống như khi di chuyển file. Trong ví dụ sau, nếu thư mục text3 tồn tại thì lệnh sẽ chuyển text2 vào bên trong text3. Nếu text3 không tồn tại, text2 sẽ được đổi tên thành text3:

    # mv text2 text3

![anh](/LinhNH/Linux/01.Timhieu_Linux/images/mv.png)
