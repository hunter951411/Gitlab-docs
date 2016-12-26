##Truy cập công khai
- [1. Khung nhìn của Project]()
<ul>
<li>[1.1. Public projects]()</li> 
<li>[1.2. Internal Projects]()</li>
<li>[1.3. Làm thế nào để thay đổi khung nhìn của các project]()</li>
</ul>
- [2. Khung nhìn của group]()
- [3. Khung nhìn của user]()
- [4. Hạn chế việc sử dụng các Public hay Internal Project]()

##Truy cập công khai
GitLab cho phép bạn thay đổi khung nhìn project của bạn để được truy cập công khai hoặc nội bộ. 

Các dự án có một trong các mức khung nhìn sẽ được liệt kê trong thư mục truy cập công cộng (/public dưới instance GitLab của bạn). Dưới đây là GitLab.com.example. 

Project internal sẽ chỉ có sẵn cho người dùng xác thực.

###1. Khung nhìn của Project
####1.1. Public projects
Các Project public có thể được cloned mà không cần bất kì xác thực nào.

Họ cũng sẽ được liệt kê trên các thư mục truy cập public (/public)

Bất kì người dùng đăng nhập sẽ có quyền Guest vào repository.

####1.2. Internal projects

Các Project Internal có thể được clone bởi bất kì người dùng đã được đăng nhập.

Họ cũng sẽ liệt kê trên các thư mục truy cập Public (/public) cho người dùng đăng nhập

Bất kì người dùng đăng nhập sẽ có quyền Guest vào repository.

####1.3. Cách để thay đổi khung nhìn của project
<ul>
<li>1. Tới Settings của project</li>
<li>2. Thay đổi "Visibility Level" để Public, Internal hay Private.</li>
</ul>

###2. Khung nhìn của Groups

```
Lưu ý: Bắt đầu với GitLab 8.6, khả năng hiển thị của nhóm đã thay đổi và có thể được cấu hình theo cách tương tự như các project. Trong các phiên bản trước đó, trang của nhóm là hiển thị với tất cả người dùng.
```

Giống như với các project, khả năng hiển thị của một nhóm có thể được thiết lập để ra lệnh cho dù người dùng ẩn danh, tất cả người dùng đã đăng nập, hoặc chỉ các thành viên của nhóm có thể xem nó. Sự hạn chế cho các tầm nhìn vào mức độ thiết lập ứng dụng cho nhóm, vì vậy nếu đó là tiết lập để Internal, trang khám phá sẽ trống cho người dùng ẩn danh. Trang của nhóm bây giờ có một biểu tượng mức hiển thị.


###3. Khung nhìn của người dùng

Các trang Public của một người dùng, đặt tại /u/username, luôn luôn nhìn thấy cho dù bạn có đăng nhập hay không.

Khi truy cập vào các trang public của một user, bạn chỉ có thể xem các dự án mà bạn có quyền.

Nếu public level bị hạn chế, hồ sơ người dùng chỉ hiện thị cho người dùng đăng nhập.

###4. Hạn chế sử dụng các project public hay project internal

Trong trang Admin dưới Settings (/admin/application_settings), bạn có thể bị hạn chế sử dụng khung hìn cho người dùng khi họ tạo ra một 
project hay một snippet. Điều này rất hữu ích để ngăn chặn cho những người dùng expose repository của họ thành public một cách tình cờ. Các thiết lập hạn chế khung nhìn không áp dụng cho người dùng admin.
