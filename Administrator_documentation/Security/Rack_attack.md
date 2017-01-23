#Tấn công Rack
Để ngăn chặn người dùng không chính đáng làm tổn hại đến GitLab sử dụng rack-attack.

Nếu bạn cài đặt và nâng cấp GitLab bằng cách làm theo các hướng dẫn chính thức này cần được kích hoạt mặc định

Nếu bạn đang thiếu config/initializers/rack_attack.rb các bước sau đây cần phthực hiện để cho phép bảo vệ ví dụ GitLab của bạn

1. Trong config/application.rb tìm và bỏ comment ở dòng sau:
```
config.middleware.use Rack::Attack
```

2. Đổi tên config/initializers/rack_attack.rb.example thành config/initializers/rack_attack.rb.

3. Xem lại paths_to_be_protected và thêm bất kỳ đường dẫn khác mà bạn cần bảo vệ

4. Khởi động lại GitLab.

Theo mặc định, người dùng đăng nhập, người dùng đăng kí nếu được kích hoạt và thiết lập lại mật khẩu người dùng được giới hạn trong 6 yêu cầu cho mỗi phút. Sau khi cố gắng trong 6 lần, khách hàng sẽ phải chờ đợt cho những phút tiếp theo để có thể thử lại. Các thiết lập này có thể được tìm thấy trong config/initializers/rack_attack.rb

Nếu bạn muốn hạn chế/ nới lỏng sử dụng giá trị limit hoặc period. Ví dụ, bạn sẽ thấy thoải mái hơn nếu thiết lập limit: 3 and period: 1.second (điều nsẽ cho phép 3 request trong vòng 1 s). Bạn cũng có thể thêm các đường dẫn khác từ danh sách bảo vệ bằng cách thêm biến paths_to_be_protected. Nếu bạn thay đổi bất kỳ các thiết lập này thì nên thực hiện khởi động lại GitLab sau đó.

Trong trường hợp bạn tìm thấy dấu hiệu là không đủ để bảo vệ bạn chống lại người dùng có ý xấu, rack_attack cung cấp danh sách IP white và IP black, bộ lọc Fail2ban và theo dõi
Để biết thêm thông tin về các tùy chọn đọc thtại [rack-attack README](https://github.com/kickstarter/rack-attack/blob/master/README.md).
