##Mục lục
- LDAP
[1. Security](#Security)
<ul>
<li>[1.1. User deletion](#UserDeletion)</li>
</ul>
[2. Configuration](#Configuration)
[3. Using an LDAP filter to limit access to your GitLab server](#LDAPfilter)
[4. Enabling LDAP sign-in for existing GitLab users](#Sign-in)
[5. Limitations](#Limitations)
<ul>
<li>[5.1. TLS Client Authentication](#TLSClient)</li>
<li>[5.2. TLS Server Authentication](#TLSServer)</li>
</ul>
[6. Troubleshooting](#Troubleshooting)
<ul>
<li>[6.1. Debug LDAP user filter with ldapsearch](#DebugLDAP)</li>
<li>[6.2. Invalid credentials when logging in](#Invalidcredential)</li>
<li>[6.3. Connection Refused](#ConnectionRefused)</li>
<li>[6.4. Login with valid credentials rejected](#validcredentials)</li>
</ul>

<a name="Security"></a>
###1. An toàn
Gitlab giả định rằng người sử dụng LDAP không thể thay đổi 'mail', 'email' hay 'userPrincipalName' thuộc tính của LDAP. Một người dùng LDAP được phép thay đổi email của họ trên mchủ LDAP có khả năng có thể đi qua bất cứ tài khoản ntrên máy chủ của bạn.
Chúng tôi khuyên bạn nên chống sử dụng tích hợp LDAP nếu người dùng LDAP của bạn được phép thay đổi thuộc tính 'mail', 'email' hay 'userPrincipalName' trên máy chủ LDAP.
<a name="UserDeletion"></a>
###1.1. Xóa người dùng
Nếu một người sử dụng bị xóa khỏi máy chủ LDAP họ sẽ bị chặn trong GitLab. Người dùng sẽ chặn ngay lập tức từ lúc đăng nhập. Tuy nhiên, có một thời gian LDAP kiểm tra bộ nhớ cache (thời gian đồng bộ) trong một giờ. Điều này có nghĩa người dùng đã đăng nhập hoặc đang sử dụng Git qua SSH vẫn có thể truy cập GitLab cho đến một giờ. Chặn thủ công người sử trong các khu vực GitLab Admin để ngay lập tức chặn tất cả truy cập.
```
Chú ý: GitLab EE hỗ trợ một thời gian đồng bộ cấu hình, với mặc định là một giờ.
```
<a name="Configuration"></a>
##2. Cấu hình
Để cho phép tích hợp LDAP bcần bổ sung các thiết lập máy chủ LDAP của bạn trong tập tin `/etc/gitlab/gitlab.rb` hay `/home/git/gitla/config/gitlab.yml`.
Có một nhiệm vụ Rake để kiểm tra cấu hình LDAP. Sau khi cấu hình LDAP sử dụng các tài liệu dưới đây xem LDAP check Rake task để xem thông tin kiểm tra LDAP với nhiệm vụ Rake
```
Chú ý: Trong gitlab EE bạn có thể cấu hình nhiều LDAP server để kết nối đến GitLab server.
```
Trước khi phiên bản 7.4, GitLab sử dụng một cú pháp khác nhau để cấu hình tích hợp LDAP. Cú pháp tích hợp LDAP cũ vẫn hoạt động nhưng có thể được loại bỏ trong tương lai. Nếu tập tin gitlab.rb hay gitlab.yml chứa các thiết lập LDAP trong cả hai cú pháp cũ và mới, chỉ có cú pháp cũ sẽ được chấp nhận và sử dụng bởi GitLab.
Cấu hình bên trong gitlab_rails['ldap_servers'] dưới đây là nhạy cảm để thụt đầu dòng không chính xác. Hảy chắc chắn thực hiện như ví dụ: (Copy paste đôi khi có thể gây ra vấn đề).
<a name="LDAPfilter"></a>
<a name="Sign-in"></a>
<a name="Limitations"></a>
<a name="TLSClient"></a>
<a name="TLSServer"></a>
<a name="Troubleshooting"></a>
<a name="DebugLDAP"></a>
<a name="Invalidcredentail"></a>
<a name="ConnectionRefused"></a>
<a name="validcredentials"></a>
