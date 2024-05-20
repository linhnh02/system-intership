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
    # cp File1 File2

![anh](/LinhNH/Linux/01.Timhieu_Linux/images/8.1.png)


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

## 9. Lệnh mv: Di chuyển tập tin và thư mục

    # mv [OPTIONS] SOURCE DESTINATION

Để di chuyển text1 từ thư mục làm việc hiện tại hiện tại sang thư mục /text2 thì bạn sẽ chạy lệnh sau: 
    # mv text1 / text2

Cú pháp để di chuyển thư mục cũng giống như khi di chuyển file. Trong ví dụ sau, nếu thư mục text3 tồn tại thì lệnh sẽ chuyển text2 vào bên trong text3. Nếu text3 không tồn tại, text2 sẽ được đổi tên thành text3:

    # mv text2 text3

![anh](/LinhNH/Linux/01.Timhieu_Linux/images/mv.png)


## 10. Lệnh file: dùng để xác định loại tệp 

    # file [OPTIONS] [filename]

![anh](/LinhNH/Linux/01.Timhieu_Linux/images/file.png)

Hiển thị tất cả các loại file trong thư mục đang đứng

    # file *

![anh](/LinhNH/Linux/01.Timhieu_Linux/images/10.1.png)


## 11. Lệnh rm (remove): dùng để xóa file (hoặc thư mục)

### 11.1 Câu lệnh xóa file
    # rm Tên_file
    -- xóa 1 file

    # rm File1 File2 File3
    -- xóa nhiều file

![anh](/LinhNH/Linux/01.Timhieu_Linux/images/11.1.png)

### 11.2 Thông báo hỏi có muốn xóa hay không
    # rm -i Tên_file
    -- i: interactive

![anh](/LinhNH/Linux/01.Timhieu_Linux/images/11.2.png)


### 11.3 Tắt bỏ ràng buộc để xóa file

    # rm -f Tên_file
    -- f: force
### 11.4 Hiển thị kết quả xóa 

    # rm -v filename
    -- v: verbose

![anh](/LinhNH/Linux/01.Timhieu_Linux/images/rm-v.png)

### 11.5 Xóa thư mục bằng lệnh rm trong Linux
Xóa thư mục rỗng

    # rm -d Tên_thư_mục

Xóa thư mục rỗng

![anh](/LinhNH/Linux/01.Timhieu_Linux/images/rm-folder.png)

Không xóa được thư mục có chứa dữ liệu (file)

![anh](/LinhNH/Linux/01.Timhieu_Linux/images/11.5.png)


### 11.6 Để xóa thư mục có dữ liệu/thư mục không rỗng và tất cả các file bên trong bằng cách đệ quy thì sử dụng cú pháp:
    # rm -r Tên_thư_mục -- r: recursive    

![anh](/LinhNH/Linux/01.Timhieu_Linux/images/photo.png)


## 12. Lệnh touch: lệnh này dùng để tạo 1 file trống hoặc thay đổi dấu thời gian (timestamps) của file.
Dấu thời gian của file có các loại sau: 
- accesstime (thời gian truy cập: thời gian lần cuối file đọc được)
- modifytime (thời gian của file được chỉnh sửa)
- changetime (thời gian lần cuối của file được thay đổi)

Cú pháp: 

    # touch [OPTIONS] File_name

Tạo nhiều file cùng 1 lúc:    
    
    # touch filename1 filename2 filename3

Hoặc cod thể tạo file bằng dấu ngoặc nhọn để tạo nhiều file như sau:

    # touch filename{1..3}.txt 
    
![anh](/LinhNH/Linux/01.Timhieu_Linux/images/12.png)


### 12.1 Thay đổi thời gian truy cập file

    # touch -a filename
    -- a: accesstime

![anh](/LinhNH/Linux/01.Timhieu_Linux/images/12.1.png)

### 12.2 Thay đổi thời gian chỉnh sửa file 

    # touch -m filename
    -- m: modifytime

![anh](/LinhNH/Linux/01.Timhieu_Linux/images/12.2.png)


### 12.3 Thay đổi thời gian truy cập và chỉnh sửa

    # touch -am filename

![anh](/LinhNH/Linux/01.Timhieu_Linux/images/12.3.png)

### 12.4 Thay đổi AccessTime mà không phải tạo file mới

    # touch -c filename

![anh](/LinhNH/Linux/01.Timhieu_Linux/images/12.4.png)


### 12.5 Đặt thời gian nhất định cho thời gian truy cập và chỉnh sửa 

    # touch -t Thời_Gian filename

![anh](/LinhNH/Linux/01.Timhieu_Linux/images/12.5.png)


Cấu trúc ngày giờ phải đúng là CCYYMMDDhhmm.ss, theo mô tả sau:

- MM – tháng trong năm [01-12]
- DD – ngày trong tháng [01-31]
- hh – giờ của ngày [00-23]
- mm – phút [00-59]
- CC – 2 số đầu của năm
- YY – 2 số cuối của năm
- SS – số giây [00-59]
  