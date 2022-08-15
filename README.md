HOSTING - ONLINE HOST

- localhost được xây dựng bởi XAMPP chỉ dùng cho mục đích kiểm thử, thực nghiệm trên cục bộ máy tính cá nhân.
- nếu cần 1 app có thể truy cập dữ liệu từ bất kỳ thời gian và địa điểm nào, thì data phải được lưu trữ online trên hosting online
- hosting giống như 1 ổ cứng online chứ không còn là ổ cứng cục bộ trên máy tính cá nhân.

___

- Hosting là 
	- dịch vụ lưu trữ dữ liệu và chia sẻ dữ liệu trực tuyến. 
	- không gian lưu trữ được chia nhỏ từ một máy chủ. 
- Dịch vụ Hosting nghĩa là thuê một không gian nhỏ trên server để lưu trữ file và dữ liệu, nội dung,… trên không gian này.
- Ví dụ: 
	- Website là ngôi nhà, 
	- còn domain chính là địa chỉ nhà 
	- thì hosting chính là miếng đất của ngôi nhà đó. 
- Vì vậy, để xây dựng website thì bạn bắt buộc phải mua đất trước.
- trong lập trình Android thì Hosting là nơi để lưu trữ data, để app có thể truy cập từ bất kỳ thời gian và địa điểm
- search google với từ khóa hosting, có rất nhiều dịch vụ cung cấp hosting: hostinger.vn, vietnix.vn, ...

___

ĐĂNG KÝ, TẠO DATABASE, IMPORT TABLE TỪ LOCAL HOST

- sau khi tìm được nhà cung cấp dịch hosting thích hợp ta tiến hành đăng ký và thanh toán chi phí ta sẽ sở hữu được 1 Hosting
- sau khi Login vào được Hosting, ta tạo Database trên Hosting đó (Database trên dịch vụ Hosting sẽ yêu cầu username và password để Login)
- để không phải tùy chỉnh lại Database và Table đã tạo ở XAMPP localhost
	- ở localhost ta tiến hành export databse
	- ở hosting ta import database

___

UPLOAD FILE PHP LÊN HOSTING

- trước khi upload các file PHP lên Hosting, ta nên chỉnh sửa các file dùng để kết nối đến Database trên Hosting với các thông tin tương ứng trên Hosting
	- tên localhost đổi thành tên hosting
	- tên user truy cập database ở localhost đổi thành tên user truy cập database ở hosting
	- nhập password truy cập database ở hosting
	- tên database ở hosting
- tất cả các thông tin cần chỉnh sửa nằm ở câu lệnh dùng để connect đến hosting của file ``dbCon.php``

```php
<?php 
// KẾT NỐI ĐẾN DATABASE
  // từ ver 5.6 ta dùng mysqli_connect và truyền vào 4 tham số dạng chuỗi:
    // "tên server lưu trữ database" (localhoast)
    // "tên user đăng nhập vào database" (mặc định của XAMPP là root)
    // "mật khẩu đăng nhập của user vào database" (mặc định của XAMPP là rỗng)
    // "tên của database" (database ta đang cần là sinhvien)
  $connect = mysqli_connect("localhost","root","","sinhvien"); // CỔNG KẾT NỐI

  // truy vấn đến cổng kết nối đã thiết lập, bước này chưa truy vấn nên ta chỉ thực hiện thiết lập kiểu định dạng utf8 để trả về tiếng việt có dấu
	mysqli_query($connect, "SET NAMES 'utf8'");
?>
```

- sau khi chỉnh sửa ta tiến hành upload trực tiếp lên hosting hoặc thông qua ứng dụng Filezilla
- sự tiện lợi của Filezilla chính là khi đã thiết lập thông số cho folder ở localhost với folder ở hosting, thì mọi thay đổi các file ở localhost sẽ được upload lên hosting để cập nhật

___

CHỈNH SỬA APP

- ở app, những url của localhost ta thay đổi tương ứng với url ở hosting