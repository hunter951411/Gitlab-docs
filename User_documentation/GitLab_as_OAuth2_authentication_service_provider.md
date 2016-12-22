##Gitlab đóng vai trò như một nhà cung cấp dịch vụ xác thực OAuth2

##Mục lục

- [1. Gitlab đóng vai trò như một nhà cung cấp dịch vụ xác thực OAuth2](#GitLabasOAuth2)
<ul>
<li>[1.1 Giới thiệu OAuth](#OauthIntro)</li>
<li>[1.2 Thêm một ứng dụng qua profile](#AddApps)</li>
<li>[1.3 Ứng dụng OAuth trong khụ vực admin](#OauthApps)</li>
<li>[1.4 Các ứng dụng cấp quyền](#AuthorizedApps)</li>
</ul>


<a name="GitLabasOAuth2"></a>
##1. Gitlab đóng vai trò như một nhà cng cấp dịch vụ xác thực OAuth2
<a name="OAuthIntro"></a>
Tài liệu này là về việc sử dụng GitLab như một nhà cung cấp dịch vụ chứng thực OAuth để đăng nhập vào các dịch vụ khác. 

Nếu bạn muốn sử dụng các nhà cung cấp dịch vụ chứng thực OAuth khác để đăng nhập vào GitLab, xin vui lòng xem tài liệu khách hàng OAuth2

###1.1 Giới thiêu OAuth
<a name="AddApps"></a>
`OAuth` cung cấp cho các ứng dụng của khách hàng một 'đảm bảo tiếp cận được giao một' tài nguyên máy chủ thay mặt cho một chủ sở hữu nguồn tài nguyên. Trong thực tế, OAuth cho phép một máy chủ ủy quyền phát hành thẻ truy cập cho các khách hàng của bên thứ ba có sự chấp thuận của chủ sở hữu tài nguyên, hoặc người dùng cuối.

OAuth là sử dụng chủ yếu như một dịch vụ Single Sign-On(SSO), nhưng bạn có thể tìm thấy rất nhiều công dụng khác nhau cho các chức năng này. Ví dụ, bạn có thể cho phép người dùng đăng nhập vào ứng dụng của bạn với tài khoản GitLab.com, hoặc GitLab.com có thể được sử dụng để xác thực cho GitLab của bạn (xem [GitLab OmniAuth](https://docs.gitlab.com/ce/integration/gitlab.html)).

GitLab hỗ trợ hai cách để thêm một ứng dụng OAuth2 mới cho một ví dụ. Bạn có thể thêm một ứng dụng như một người sử dụng thường xuyên hoặc thêm nó vào khu vực admin. Điều này có nghĩa là GitLab thực sự có thể có trường hợp toàn và sử dụng rộng rãi các ứng dụng. Không có sự khác biệt giữa chúng ngoại trừ các mức khác nhau cho phép chúng được thiết lập (user / admin). URL gọi lại mặc định là `http://your-gitlab.example.com/users/auth/gitlab/callback`
###1.2 Thêm một ứng dụng qua profile
<a name="OAuthApps"></a>
Để thêm một ứng dụng mới thông qua hồ sơ của bạn, điều hướng đến <b>Profile Setting</b> > <b>Applicaitons</b> và chọn <b>New Application</b>.

Trong khung Application, nhập <b>Name</b> (tùy ý), và chắc chắn để thiết lập một cách chính xác các <b>URI Redirect</b> là URL mà người dùng sẽ được gửi sau khi họ ủy quyền với GitLab.
<img src="https://github.com/hunter951411/gitlab/blob/master/images/AddingApps.png">
Khi bạn nhấn <b>Submit</b>, bạn sẽ được cung cấp các ứng dụng ID và ứng dụng bí mật nơi mà bạn có thể sử dụng với các ứng dụng của bạn kết nối với GitLab.
<img src="https://github.com/hunter951411/gitlab/blob/master/images/SubmitApps.png">
Để tạo ra một ứng dụng mà không thuộc về một người dùng nhất định, bạn có thể tạo ra nó từ khu vực admin.

###1.3 Ứng dụng OAuth trong khu vực Admin
<a name="OauthApps"></a>
<img src="https://github.com/hunter951411/gitlab/blob/master/images/Admin%20Area.png">
Mỗi ứng dụng mà bạn được phép sử dụng thông tin GitLab của bạn sẽ được hiển thị trong phần <b>Authorized Applications</b> phần dưới <b>Profile Settings > Application</b>.

###1.4 Các ứng dụng cấp quyền
<a name="AuthorizedApps"></a>

Như bạn có thể thấy, phạm vi `api` mặc định được sử dụng, đó là phạm vi chỉ rằng GitLab hỗ trợ cho đến nay. Bất cứ lúc nào bạn có thể thu hồi bất kỳ truy cập bằng cách chỉ cần nhấp vào <b>Revoke</b>.
