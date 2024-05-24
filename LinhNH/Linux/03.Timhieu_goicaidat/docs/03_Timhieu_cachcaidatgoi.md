# Tìm hiểu về cách cài đặt các gói trên hệ điều hành Ubuntu

## Về Linux

### 1. Cập nhật cơ sở dữ liệu với gói apt (advanced package tool)

apt thực sự hoạt động trên cơ sở dữ liệu của các gói có sẵn. Nếu cơ sở dữ liệu không được cập nhật, hệ thống sẽ không biết liệu có gói nào mới hơn không. Đây là lý do tại sao việc cập nhật kho lưu trữ phải là việc đầu tiên cần làm trong bất kỳ hệ thống Linux nào sau khi cài đặt mới.

Việc cập nhật cơ sở dữ liệu gói yêu cầu đặc quyền siêu người dùng nên bạn sẽ cần sử dụng sudo

        sudo apt update

Khi chạy lệnh này, bạn sẽ thấy thông tin gói được truy xuất từ nhiều máy chủ khác nhau.


![anh](/LinhNH/Linux/03.Timhieu_goicaidat/images/apt.png/)  

Trong đó: 
- Hit (Lượt truy cập): không có thay đổi nào trong phiên bản gói so với phiên bản trước
- Get (Bỏ qua): gói đang bị bỏ qua. Gói này quá mới nên thậm chí không thèm kiểm tra hoặc đã xảy ra lỗi khi truy xuất tệp nhưng lỗi không đáng kể, nên nó bị bỏ qua.
- Ig (Nhận): Đã có phiên bản mới, nó sẽ tải xuống thông tin về phiên bản (không phải về gói đó).

### 2. Nâng cấp các gói đã cài đặt với apt

Khi bạn đã cập nhật cơ sở dữ liệu gói, bây giờ bạn có thể nâng cấp các gói đã cài đặt. Cách thuận tiện nhất là nâng cấp tất cả các gói có bản cập nhật sẵn có. Bạn chỉ có thể sử dụng lệnh dưới đây:

        sudo apt upgrade

Điều này sẽ cho bạn thấy có bao nhiêu và tất cả các gói sẽ được nâng cấp.

![anh](/LinhNH/Linux/03.Timhieu_goicaidat/images/upgrade.png/)  

Có 1 cách khác để cung cấp bản nâng cấp hoàn chỉnh bằng cách sử dụng lệnh bên dưới

        sudo apt full-upgrade

### 3. Sự khác biệt giữa cập nhật apt và nâng cấp apt 

- Lệnh `apt update` tải xuống thông tin gói từ tất cả các nguồn được định cấu hình (tức là các nguồn được định cấu hình bên trong `/etc/apt/sources.list`). Đây là cách hệ thống biết gói nào có sẵn để nâng cấp và nơi lấy phần mềm đó.

- Lệnh `apt upgrade` sau đó có thể dựa trên thông tin này và nâng cấp tất cả các gói đã cài đặt lên phiên bản mới nhất của chúng. Lệnh này sẽ chỉ nâng cấp các gói đã được cài đặt, nó sẽ không cài đặt các gói mới trừ khi chúng được yêu cầu để giải quyết các phần phụ thuộc. `apt upgrade` cũng sẽ không xóa bất kỳ gói nào, nếu một gói phải được xóa để hoàn tất nâng cấp, lệnh sẽ chỉ cần bỏ qua nâng cấp đó và giữ nguyên các gói hiện tại của bạn.
Đây là lý do tại sao cách cập nhật hệ thống Ubuntu nhanh nhất và thuận tiện nhất bằng cách sử dụng lệnh này:

        sudo apt update && sudo apt upgrade -y

### 4. Cách cài đặt gói mới với apt

        sudo apt install [packgae_name]

    _Cài đặt nhiều gói_

        sudo apt install package1 package2 package3

### 5. Cách cài đặt gói mà không cần nâng cấp

        sudo apt install package_name --no-upgrade

### 6. Nâng cấp gói mà không cài đặt

        sudo apt install package_name --only-upgrade

### 7. Cách cài đặt một phiên bản cụ thể của ứng dụng

        sudo apt install package_name = version_number

### 8. Cách xóa các gói đã cài đặt 

        sudo apt remove package_name


### 9. Tìm kiếm gói

    Chỉ cần sử dụng lệnh này với cụm từ tìm kiếm mong muốn, nó sẽ tìm thấy tất cả các gói có chứa cụm từ tìm kiếm.

        apt search <search term>

### 10. Xem nội dung của gói

        apt show package_name

Lệnh này sẽ hiển thị thông tin về (các) gói nhất định như các gói phụ thuộc, kích thước cài đặt và tải xuống, các nguồn khác nhau mà gói có sẵn, mô tả nội dung của gói cùng với những thứ khác.

### 11. Liệt kê các phiên bản có thể nâng cấp và cài đặt

Lệnh apt có một tùy chọn mới gọi là list, sử dụng lệnh này có thể thấy tất cả các gói phiên bản mới hơn sẵn sàng được nâng cấp

        sudo list --upgradable

   
Có thể xem tất cả các gói đã cài đặt trên hệ thống với tùy chọn đã cài đặt:

        apt list --installed

Ngoài ra có thêm tùy chọn để liệt kê tất cả các gói có sẵn cho hệ thống của bạn:

        apt list --all-versions

### 12. Dọn dẹp hệ thống

        sudo apt autoremove

Lệnh này loại bỏ các lib và gói được cài đặt tự động để đáp ứng sự phụ thuộc của gói đã cài đặt. Nếu gói bị gỡ bỏ, các gói được cài đặt tự động này dù vô dụng nhưng vẫn còn trong hệ thống.        