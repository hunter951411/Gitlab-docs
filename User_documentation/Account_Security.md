#Xác thực hai chiều

##Tùy chọn phục hồi 

Nếu bạn bị mất điện thoại tạo ra mã của bạn (chẳng hạn như điện thoại di động của bạn) và bạn cần phải vô hiệu hóa xác thực hai yếu tố trên tài khoản của bạn, bạn có nhiều lựa chọn. 

###Sử dụng lưu mã phục hồi 

Khi bạn kích hoạt xác thực hai yếu tố cho tài khoản của bạn, một loạt các mã phục hồi được tạo ra. Nếu bạn lưu lại những mã ở nơi an toàn, bạn có thể sử dụng để đăng nhập. 

Đầu tiên, nhập tên tài khoản của bạn (hoặc email) và mật khẩu vào trang đăng nhập GitLab. Khi được nhắc nhở cho một mã hai yếu tố, nhập một trong các mã khôi phục bạn đã lưu trước đó. 

```
Lưu ý: Khi một mã phục hồi đặc biệt đã được sử dụng, nó không thể được sử dụng lại. Bạn vẫn có thể sử dụng mã phục hồi lưu khác tại một thời gian sau đó.
```
##Tạo ra một mã phục hồi mới sử dụng SSH

Đó không phải là cách không phổ biến cho người sử dụng để quên lưu các mã phục hồi khi cho phép xác thực hai yếu tố. Nếu bạn có một khoá SSH thêm vào tài khoản GitLab của bạn, bạn có thể tạo ra một tập mới của mã phục hồi bằng SSH. 

Chạy câu lệnh $ssh git@gitlab.example.com 2fa_recovery_codes. Bạn sẽ được nhắc nhở để xác nhận rằng bạn muốn tạo ra mã mới. Nếu bạn chọn tiếp tục, bất kỳ mã đã lưu trước đó sẽ bị vô hiệu.

```
$ ssh git@gitlab.example.com 2fa_recovery_codes
Are you sure you want to generate new two-factor recovery codes?
Any existing recovery codes you saved will be invalidated. (yes/no)
yes
Your two-factor authentication recovery codes are:

119135e5a3ebce8e
11f6v2a498810dcd
3924c7ab2089c902
e79a3398bfe4f224
34bd7b74adbc8861
f061691d5107df1a
169bf32a18e63e7f
b510e7422e81c947
20dbed24c5e74663
df9d3b9403b9c9f0

During sign in, use one of the codes above when prompted for
your two-factor code. Then, visit your Profile Settings and add
a new device so you do not lose access to your account again.
```

Tiếp theo, đi đến rang đăng nhập GitLab và nhập tên tài khoản của bạn (hoặc email) và mật khẩu. Khi được nhắc nhở cho một mã hai yếu tố, nhập một trong các mã phục hồi thu được từ đầu ra dòng lệnh. 

```
Lưu ý: Sau khi đăng nhập, bạn phải ngay lập tức vào trang Profile Setting -> Account to set up two-factor authentication with a new device. (Tài khoản để thiết lập xác thực hai yếu tố với một thiết bị mới.) 
```

Hỏi quản trị GitLab để vô hiệu hóa hai yếu tố trên tài khoản của bạn 

Nếu hai phương pháp trên là không thể, bạn có thể yêu cầu quản trị toàn cầu GitLab để vô hiệu hóa xác thực hai yếu tố cho tài khoản của bạn. Xin lưu ý rằng điều này sẽ tạm thời rời khỏi tài khoản của bạn ở trong tình trạng kém an toàn. Bạn nên đăng nhập và kích hoạt xác thực hai yếu tố càng sớm càng tốt sau khi quản trị vô hiệu hóa nó.
