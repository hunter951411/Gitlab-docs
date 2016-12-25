##Bắt đầu sử dụng Git trên dòng lệnh 
- [1. Mở shell](#openshell) 
- [2. Kiểm tra nếu Git đã được cài đặt](#checkgit) 
- [3. Thêm tên người dùng Git của bạn và thiết lập email của bạn](#addgit) 
- [4. Kiểm tra thông tin của bạn](#checkinfo) 
- [5. Lệnh Git cơ bản](#basicgit) 
<ul>
<li>[5.1 Tới các nhánh master để kéo những thay đổi mới nhất từ đó](#gotothemaster) 
<li>[5.2 Tải về những thay đổi mới nhất trong project](#downloadthelatest) 
<li>[5.3 Tạo một nhánh mới](#createbranch) 
<li>[5.4 Làm việc trên một nhánh đã được tạo ra](#workonbranch)
<li>[5.5 Xem những thay đổi bạn đã thực hiện](#viewthechange) 
<li>[5.6 Thêm thay đổi với commit](#addchange) 
<li>[5.7 Gửi thay đổi đến gitlab.com](#sendchange) 
<li>[5.8 Xóa tất cả các thay đổi trong Git repository, nhưng để lại những thứ unstaged](#leaveunstaged) 
<li>[5.9 Xóa tất cả các thay đổi trong kho Git, bao gồm các file untracked](#includinguntracked) 
<li>[5.10 Hợp nhất nhánh tạo ra với chi nhánh master](#mergebranch) 
<li>[5.11 Hợp nhất nhánh master với các nhánh được tạo](#mergemaster)
</ul>

Nếu bạn bắt đầu sử dụng Git và GitLab, chắc chắn rằng bạn đã tạ và đăng nhập tài khoản trong GitLab

<a name="openshell"></a>
###1. Mở shell 
- Phụ thuộc vào hệ điều hành của bạn, bạn sẽ cần sử dụng một shell phụ mà bạn yêu thích. Đây là một số gợi ý:
<ul>
<li>Terminal trong Mac OSX</li>
<li>GitBash trong Windows</li>
<li>Linux Terminal trong Linux</li>
</ul>

<a name="checkgit"></a>
###2. Kiểm tra nếu Git đã được cài đặt
Git thường được cài đặt sẵn trên MAC và Linux.
Sử dụng câu lệnh sau để kiểm tra
```
git --version
```
Bạn sẽ nhận được một thông điệp rằng sẽ cho bạn biết Git phiên bản mà bạn có trên máy tính của bạn. Nếu bạn không nhận được một tin nhắn 'phiên bản Git', nó có nghĩa là bạn cần phải tải về [Git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git).

Nếu Git không tự động tải về, có một tùy chọn trên trang web để tải về bằng tay. Sau đó làm theo các bước trên cửa sổ cài đặt. 

Sau khi bạn đã hoàn tất cài đặt, mở một shell mới và gõ 'git --version' một lần nữa để xác minh rằng nó đã được cài đặt đúng.

<a name="addgit"></a>
###3. Thêm tên người dùng Git của bạn và thiết lập email của bạn
Điều quan trọng là để cấu hình tên Git của bạn và địa chỉ email như mọi Git cam kết sẽ sử dụng thông tin này để xác định bạn là tác giả. 

Mở shell của bạn, gõ lệnh sau để thêm tên người dùng của bạn:
```
git config --global user.name "YOUR_USERNAME"
```
Sau đó, xác minh rằng bạn có đúng tên người dùng:
```
git config --global user.name
```
Để xác định địa chỉ email của bạn, gõ câu lệnh phía dưới:
```
git config --global user.email "your_email_address@example.com"
```
Để xác minh rằng bạn đã nhập vào email của bạn một cách chính xác, loại:
```
git config --global user.email
```
Bạn sẽ cần phải làm điều này một lần duy nhất khi bạn đang sử dụng các tùy chọn `--global`. Nó nói với Git để luôn luôn sử dụng các thông tin này cho bất cứ điều gì bạn làm trên hệ thống đó. Nếu bạn muốn ghi đè này với một tên người dùng hoặc địa chỉ email khác nhau cho các project cụ thể, bạn có thể chạy các lệnh mà không có sự lựa chọn `--global` khi bạn đang ở trong project đó.

<a name="checkinfo"></a>
###4. Kiểm tra thông tin của bạn
Để xem các thông tin mà bạn đã nhập, gõ:
```
git config --global --list
```

<a name="basicgit"></a>
###5. Lệnh Git cơ bản

<a name="gotothemaster"></a>
####5.1 Tới các nhánh master để kéo những thay đổi mới nhất từ đó
```
git checkout master
```

<a name="downloadthelatest"></a>
####5.2 Tải về những thay đổi mới nhất trong project
Điều này là dành cho bạn để làm việc trên một bản sao up-to-date (điều quan trọng để làm mỗi khi bạn làm việc trên một dự án), trong khi bạn thiết lập theo dõi các nhánh.
```
git pull REMOTE NAME-OF-BRANCH -u
```
(REMOTE: origin) (NAME-OF-BRANCH : có thể là 'master' hoặc một nhánh đã có)

<a name="createbranch"></a>
####5.3 Tạo một nhánh mới
Phím "space" sẽ không được công nhận, vì vậy bạn sẽ cần phải sử dụng một dấu gạch ngang hoặc gạch dưới.
```
git checkout -b NAME-OF-BRANCH
```

<a name="workonbranch"></a>
####5.4 Làm việc trên một nhánh đã được tạo ra
```
git checkout NAME-OF-BRANCH
```

<a name="viewthechange"></a>
####5.5 Xem những thay đổi bạn đã thực hiện
Điều quan trọng là phải nhận thức được những gì đang xảy ra và những gì tình trạng thay đổi của bạn.
```
git status
```

<a name="addchange"></a>
####5.6 Thêm thay đổi với commit
Bạn sẽ thấy những thay đổi của bạn trong màu đỏ khi bạn gõ "git status".
```
git add CHANGES IN RED
git commit -m "DESCRIBE THE INTENTION OF THE COMMIT"
```

<a name="sendchange"></a>
####5.7 Gửi thay đổi đến gitlab.com
```
git push REMOTE NAME-OF-BRANCH
```

<a name="leaveunstaged"></a>
####5.8 Xóa tất cả các thay đổi trong Git repository, nhưng để lại những thứ unstaged
```
git checkout .
```

<a name="includinguntracked"></a>
####5.9 Xóa tất cả các thay đổi trong kho Git, bao gồm các file untracked
```
git clean -f
```

<a name="mergebranch"></a>
####5.10 Hợp nhất nhánh tạo ra với chi nhánh master
Bạn cần tạo ra một nhánh mới
```
git checkout NAME-OF-BRANCH
git merge master
```

<a name="mergemaster"></a>
####5.11 Hợp nhất nhánh master với các nhánh được tạo
Bạn cần phải ở trong nhánh master
```
git checkout master
git merge NAME-OF-BRANCH
```
