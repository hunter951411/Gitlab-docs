##Khung nhìn và điều khiển truy cập
##Bật giao thức truy cập Git
```
Giới thiệu trong GitLab 8.10.
```
Với hạn chế truy cập của Gitlab bạn có thẻ chọn nơi giao thức truy cập Git mà bạn muốn người dùng có bạn giao tiếp với Gitlab. Tính năng này có thể bật thông qua `Application Settings` trong giao diện Admin
- Cài đặt gọi là `Enabled Git access protocols`, nó ch phép bạn chọn giữa các tùy chọn:
<ul>
<li>Cả SSH và HTTP(s)</li>
<li>Chỉ sử dụng SSH</li>
<li>Chỉ sử dụng HTTP(s)</li>
</ul>
Khi chọn cả SSH và HTTP(s) được bật lên, GitLab sẽ làm việc như bình thường, nó sẽ cung ccho người dùng của bạn tuy chọn để lựa chọn giao thức mà họ muốn sử dụng
- Khi bạn chọn chỉ cho phép một trong các giao thức, một vài điều sẽ xảy ra:
<ul>
<li>Các trang trong project sẽ chỉ cho phép URL của protocol được hiển thị,không có tùy chon để  thay đổi nó.</li>
<li>Một tooltip sẽ hiển thị khi bạn di chuôt qua giao thức của URL, nếu một động tác của người dùng được yêu cầu. Ví dụ: Thêm một khóa SSH,hoặc thiết lập một mật khẩu</li>
</ul>
Ở phía trên của hạn chế giao diện người dùng, GitLab sẽ từ chối tất cả các hành động Git trên giao thức không được lựa chọn.
```
Lưu ý: Hãy ghi nhớ rằng vvô hiệu hóa một giao thức trcập không thực sự ngăn chặn sự truy cập vào các máy chủ của chính nó. Các cổng vẫn được sử dụng cho các giao thức có thể là SSH hoặc HTTP, vẫn có thể truy câp. Gitlab chỉ làm hạn chế truy cập vào mức độ ứng dụng.
```
