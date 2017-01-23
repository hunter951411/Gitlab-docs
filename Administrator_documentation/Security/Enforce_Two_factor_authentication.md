# Thực thi Xác thực 2 yếu tố (2FA)

Xác thực 2 yếu tố (2FA) cung cấp một mức độ bảo mật bổ sung vào tài khoảng GitLab của người dùng. Khi được kích hoạt, ngoài việc cung cấp username và password để đăng nhập, họ sẽ được nhắc nhở cho một mã được tạo ra bởi một ứng dụng điện thoại của họ.

Có thể đọc thêm về nó ở đây: [Xác thực hai yếu tố]()

Việc kích hoạt 2F

Người dùng trên GitLab, có thể cho phép nó không can thiệp nào của admin. Nếu bạn muốn thực thi tất cả mọi người để thiết ập 2FA, bạn có thể lựa chọn hai cách khác nhau:

1. Thực thi trên đăng nhâp tiếp theo.
2. Đề nghị trên đăng nhập tiếp theo, nhưng cho phép một thời gian giới hạn trước khi thực thi.

Trong khu vực Admin Area ở phần Setting ( /admin/application_settings), tìm kiếm "Sign-in Restrictions" area, nơi bạn có thể cấu hình cả hai.

Nếu bạn muốn thực thi 2FA sẽ có hiệu lực đăng nhập tiếp theo, thay đổi grace period thành 0
