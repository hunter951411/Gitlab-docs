## Tùy chỉnh giới hạn độ dài mật khẩu

Nếu bạn muốn thực thi mật khẩu người dùng có thể thực hiện thêm các bước sau:

Nếu bạn không sử dụng tùy chọn độ dài mật khẩu `devise_password_length.rb` thì mật khẩu được đặt là tối thiểu 8 kí tự trong `config/initializers/devise.rb`.

```
cd /home/gitlab
sudo -u git -H cp config/initializers/devise_password_length.rb.example config/initializers/devise_password_length.rb
sudo -u git -H editor config/initializers/devise_password_length.rb
```
