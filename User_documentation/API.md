##GitLab API
###Mục Lục
- [1. Resources](#resources)
<ul>
<li>	[1.1. Internal CI API](#internalciapi)</li>
</ul>
- [2. Authentication](#authentication)
<ul>
<li>	[2.1. Private Tokens](#privatetokens)</li>
<li>	[2.2. OAuth 2 Tokens](#oauth2tokens)</li>
<li>	[2.3. Personal Access Tokens](#personalaccesstokens)</li>
<li>	[2.4. Session Cookie](#sessioncookie)</li>
</ul>
- [3. Basic Usage](#basicusage)
- [4. Status codes](#statuscodes)
- [5. Sudo](#sudo)
- [6. Pagination](#pagination)
<ul>
<li>  [6.1. Pagination Link header](#paginationlinkheader)</li>
<li>  [6.2. Other pagination headers](#otherpaginationheaders)</li>
</ul>
- [7. id vs iid](#idvsidd)
- [8. Data validation and error reporting](#datavalidationanderrorreporting)
- [9. Unknown route](#unknownroute)
- [10. Clients](#clients)

##GitLab API

Tự động hóa GitLab qua một API đơn giản và mạnh mẽ. Tất cả các định nghĩa có thể được tìm thấy dưới  `/lib/api`.
<a name="resources"></a>
###1. Resources (Tài nguyên)
Tài liệu cho nguồn API khác nhau có thể được tìm thấy trong các địa điểm sau:
<ul>
<li>Award Emoji</li>
<li>Branches</li>
<li>Broadcast Messages</li>
<li>Builds</li>
<li>Build Triggers</li>
<li>Build Variables</li>
<li>Commits</li>
<li>Deployments</li>
<li>Deploy Keys</li>
<li>Gitignores templates</li>
<li>GitLab CI Config templates</li>
<li>Groups</li>
<li>Group Access Requests</li>
<li>Group Members</li>
<li>Issues</li>
<li>Issue Boards</li>
<li>Keys</li>
<li>Labels</li>
<li>Merge Requests</li>
<li>Milestones</li>
<li>Open source license templates</li>
<li>Namespaces</li>
<li>Notes (comments)</li>
<li>Notification settings</li>
<li>Pipelines</li>
<li>Projects including setting Webhooks</li>
<li>Project Access Requests</li>
<li>Project Members</li>
<li>Project Snippets</li>
<li>Repositories</li>
<li>Repository Files</li>
<li>Runners</li>
<li>Services</li>
<li>Session</li>
<li>Settings</li>
<li>Sidekiq metrics</li>
<li>System Hooks</li>
<li>Tags</li>
<li>Todos</li>
<li>Users</li>
<li>Validate CI configuration</li>
<li>Version</li>
</ul>
<a name="internalciapi"></a>
####1.1. Internal CI API (CI API nội bộ)
Các tài liệu sau đây là dành cho các API CI nội bộ:
<ul>
<li>Builds</li>
<li>Runners</li>
</ul>
<a name="authentication"></a>
###2. Authentication (Xác thực)
Tất cả các yêu cầu API yêu cầu xác thực thông qua một phiên cookie hoặc token. Có ba loại thẻ có sẵn: private tokens, OAuth 2 tokens, và thẻ truy cập cá nhân. 

Nếu thông tin xác thực không hợp lệ hoặc bỏ qua, một thông báo lỗi sẽ được trả lại với mã trạng thái 401:
```
{
  "message": "401 Unauthorized"
}
```
<a name="privatetokens"></a>
####2.1 Private Tokens
Bạn cần phải vượt qua một tham số private_token qua chuỗi truy vấn hoặc tiêu đề. Nếu được thông qua như là một tiêu đề, tên tiêu đề phải được `PRIVATE-TOKEN` (chữ hoa và với một dấu gạch ngang thay vì một gạch dưới). Bạn có thể tìm thấy hoặc thiết lập lại thẻ riêng của bạn trong trang tài khoản của bạn `(/profile/account)`.
<a name="oauth2tokens"></a>
####2.2 OAuth 2 Tokens
Bạn có thể sử dụng mã thông báo OAuth 2 để xác thực với các API bằng cách đi qua nó hoặc trong các tham số access_token hoặc trong Authorization header(tiêu đề ủy quyền). 

Ví dụ về sử dụng thẻ OAuth2 trong tiêu đề:
`curl --header "Authorization: Bearer OAUTH-TOKEN" https://gitlab.example.com/api/v3/projects`

<a name="personalaccesstokens"></a>
####2.3 Personal Access Tokens
`Được giới thiệu vào GitLab 8. 8.`

Bạn có thể tạo nhiều thẻ truy cập cá nhân như bạn muốn từ hồ sơ GitLab của bạn (/profile/personal_access_tokens); có lẽ một cho mỗi ứng dụng cần truy cập vào các API GitLab. 

Một khi bạn có thẻ của bạn, vượt qua nó để các API bằng cách sử dụng các tham số private_token hoặc tiêu đề PRIVATE-TOKEN.
<a name="sessioncookie"></a>
####2.4 Session Cookie
Khi đăng nhập vào GitLab như một người dùng bình thường, một cookie _gitlab_session được thiết lập. API sẽ sử dụng cookie này để xác thực nếu nó hiện diện, nhưng bằng cách sử dụng API để tạo ra một cookie phiên làm việc mới hiện chưa được hỗ trợ.
<a name="basicusage"></a>
###3. Basic Usage (Sử dụng cơ b)
Yêu cầu API nên được bắt đầu với `api` và phiên bản API. Các phiên bản API được định nghĩa trong lib `/api.rb`. 

Ví dụ về một yêu cầu API hợp lệ:
`GET https://gitlab.example.com/api/v3/projects?private_token=9koXpg98eAheJpvBs5tK`
Ví dụ về một yêu cầu API giá trị sử dụng cURL và xác thực thông qua tiêu đề:
`curl --header "PRIVATE-TOKEN: 9koXpg98eAheJpvBs5tK" "https://gitlab.example.com/api/v3/projects"`
Các API sử dụng JSON để tuần tự hóa dữ liệu. Bạn không cần phải chỉ định `.json` vào cuối URL API.
<a name="statuscodes"></a>
###4. Status Codes (Mã trạng thái)
Các API được thiết kế để trở lại tình trạng mã số khác nhau tùy theo bối cảnh và hành động. Bằng cách này, nếu một yêu cầu dẫn đến một lỗi, người gọi có thể để có được cái nhìn sâu sắc vào những gì đã đi sai. 

Bảng dưới đây đưa ra một cái nhìn tổng quan về cách các hàm API thường cư xử.
|<b>Request type</b>| <b>Description</b>|
|-------------------|-------------------|
|`GET`|Truy cập một hoặc nhiều nguồn và trả về kết quả như JSON.|
|`POST`|Trả về `201 Created` nếu tài nguyên được tạo thành công và trả lại tài nguyên mới được tạo ra như là JSON.|
|`GET/ PUT/ DELETE`|Trả về `200 OK` nếu tài nguyên được truy cập, sửa đổi hoặc xóa thành công. Các (sửa đổi) kết quả được trả về là JSON.|
|`DELETE`|Được thiết kế để được idempotent, có nghĩa là một yêu cầu đến một tài nguyên vẫn trả về `200 OK` ngay cả khi nó đã bị xóa trước hoặc là không có sẵn. Lý do đằng sau này, đó là người dùng không thực sự quan tâm nếu tài nguyên tồn tại trước hay không.|

Bảng dưới đây cho thấy các mã trả có thể cho yêu cầu API.
<a name="sudo"></a>
###5. Sudo


<a name="pagination"></a>
###6. Pagination

<a name="paginationlinkheader"></a>
####6.1. Pagination Link header

<a name="otherpaginationheaders"></a>
####6.2. Other pagination headers


<a name="idvsidd"></a>
###7. Id vs Sidd


<a name="datavalidationanderrorreporting"></a>
###8. Data Validation and Error Reporting


<a name="unknownroute"></a>
###9. Unkown Route


<a name="clients"></a>
###10. Clients
