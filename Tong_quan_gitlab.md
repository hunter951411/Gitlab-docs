#I. Tổng quan về GitLab

##1. GitLab là gì?

- GitLab khá nổi tiếng và là một mã nguồn mở của máy chủ Git được thực hiện bởi hơn 50.000 tổ chức. Trong vài năm gần đây Gitlad đã phát triển mạnh mẽ với sự hỗ trợ của cộng đồng mạng, hàng nghìn người sử dụng trên một máy chủ duy nhất hoặc một số máy chủ hoạt động tương tự. Nếu bạn cần thiết lập một máy chủ Git, thì GitLab cung cấp cho bạn một giải pháp hoàn hảo.
- Gitlab là một hệ thống self-hosted để quản lý mã nguồn của bạn. Bản đầu tiên được phát hành vào tháng 10/2011 và được cập nhật vào ngày 22 hàng tháng. Gitlab được phát hành theo tiêu chuẩn của MIT.
- Gitlab được thành lập bởi Dmitriy Zaporozhets năm 2013. Dự án bao gồm hai nhóm chính: một bên là “open source core team” và một bên là “GitLab B.V. team” (chi nhánh của công ty Gitlab).
- GitLab được sử dụng để lư trữ trên Github, nhưng với sự nỗ lực của Dmitriy Zaporozhets suốt một năm làm việc tại GitLab, kể từ tháng 1/2014 mã nguồn được lưu trữ trên sever chính của gitlab là gitlab.com. Các nhánh của GitLab được lưu trữ trên github, sẽ hoạt động như một source, nơi bạn có thể pull, push và merge các yêu cầu.

##2. Đặc điểm của GitLab

###GitLab hỗ trợ ba phiên bản:

- Gitlab community editon (CE) - Gitlab phiên bản cộng đồng: là phiên bản mã nguồn mở. Được cung cấp qua Git từ kho lưu trữ chứa gitlab. Phiên bản mới nhất của gitlab được các nhà phát triển release tại các nhánh stable và nhánh master.
- Gitlab enterprise edition (EE) - Gitlab phiên bản doanh nghiệp: là phiên bản có sẵn không lâu sau khi phát hành bản CE, được cung cấp từ kho lưu trữ của gitlab.com. Một doanh nghiệp đăng lý GitLab được sự support của GitLad BV những khó khăn khi cài đặt.
- Gitlab continuous intergration (CI): là một giải pháp tích hợp được thực hiện bở nhóm phát triển Gitlab

###Protected branches:

- Gitlab cho phép đọc hoặc ghi vào repository và các branches.
- Để cấp quyền cho những người được phép commit và pushing code, gitlad đã tạo ra protected branches.
- Một protected branch gồm 3 điều cơ bản sau:
<ul>
<li>Ngăn chặn việc push từ tất cả mọi người trừ user và master.</li>
<li>Ngăn chặn việc push code lên branch từ những người không có quyền truy cập.</li>
<li>Ngăn chặn bất kỳ ai thực hiện xóa branch.</li>
</ul>
- Bạn có thể tạo bất kỳ branch từ một protected branch. Gitlad mặc định master branch là protected branch.
- Để bảo mật một branch, user cần có ít nhất một quyền cho phép từ master branch.

###Tầng vật lý của GitLab

- Kho lưu trữ: xử lý các dự án trong Gitlab. Các sản phẩm lưu trữ (như dự án) có thể được lưu trữ tại warehouse. Nó có thể là một đĩa cứng hoặc một cái gì đó phức tạp hơn như hệ thống tập tin NFS.
- Nginx hoạt động giống như front-desk. Người sử dụng đến Nginx và yêu cầu hành động được thực hiện bởi worker trong văn phòng.
- Cơ sở dữ liệu là một loạt các file của các metal file cabinets với các thông tin về:
- Các sản phẩm trong warehouse (siêu dữ liệu, issuse, các yêu cầu merge ...).
- Người sử dụng đến front-desk (permissions).
- Redis: là phần giao tiếp một broad với cubby holes- cái mà có thể chứa các nhiệm vụ, yêu cầu cho worker.
- Sidekiq là một worker, công việc chủ yếu là xử lý việc gửi email. Nó nhận nhiệm vụ từ Redis.
- A Unicorn worker: là một nhân viên xử lý các nhiệm vụ nhanh chóng và dễ. Học làm việc với Redis. Công việc của họ gồm:
- Kiểm tra quyền truy cập bằng cách kiểm tra các session của người dùng được lưu trữ trong Redis cubby hole.
- Làm nhiệm vụ cho Sidekiq.
- Lấy công cụ từ warehouse hoặc di chuyển mọi thứ xung quanh trong đó
- Gitlab-shell: là loại thứ ba của worker, nhiệm vụ của nó là tạo các đơn đặt hàng từ một máy fax (SSH) thay vì front-desk (HTTP). Gitlab-shell giao tiếp với Sidekiq qua Redis và hỏi những câu hỏi nhanh của Unicorn worker hoặc trực tiếp hoặc qua front-desk.
- Gitlab enterprise edition (ứng dụng) là tập hợp các quy trình và hoạt động kinh doanh được điểu hành bởi ofice (văn phòng).

###System layout

- Khi đề cập đến Git trong những hình ảnh có nghĩa là thư mục home của người sử dụng Git thường là /home/git.
- Repositories bare nằm trong đường dẫn /home/git/repositories. Gitlab là một ứng dụng ruby on ralis do đó để biết rõ các hoạt động bên trong bạn có thể tìm hiểu bằng cách tìm hiểu về hoạt động của ruby on ralis.
- Để sử dụng kho dữ liệu qua SSH có một ứng dụng thêm vào được gọi là gitlab-sell cái mà được cài đặt tại /home/git/gitlab-shell.


###Components

<img src="https://github.com/hunter951411/gitlab/blob/master/component.png">
