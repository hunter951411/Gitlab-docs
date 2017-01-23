###Làm thế nào để thiết lập lại mật khẩu máy user root của bạn.
Đăng nhập vào máy chủ của bạn với quyền root. Sau đó bắt đầu một Ruby on Rails console. 
Bát đầu giao diện bằng lệnh này:
```
gitlab-rails console production
```

Chờ đến khi giao diện điều khiển đã được nạp.
Có nhiều cách để thấy người dùng của bạn. Bạn có thể tìm kiếm email hoặc tên người dùng.
```
user = User.where(id: 1).first
```
hoặc
```
user = User.find_by(email: 'admin@localhost')
```
Bây giờ bạn có thể thay đổi mật khẩu của bạn:
```
user.password = 'secret_pass'
usser.password_confirmation = 'secret_pass'
```
Điều quan trọng là bạn nên sử dụng cả password và password_confirmation để làm cho nó làm việc.
Đừng quên lưu các thay đổi

```
user.save!
```

Thoát khỏi giao diện điều khiển và thử đăng nhập bằng mật khẩu mới.
