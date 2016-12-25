##Các lệnh cơ bản

###Mục lục
 
- [1. Bắt đầu làm việc với các project](#startworking)
- [2. Trên giao diện dòng lệnh](#commandline)
<ul>
<li>[2.1 Clone dự án của bạn](#cloneproject)</li> 
<li>[2.2 Đi vào một project, thư mục hoặc tập tin để làm việc trong đó](#gointoproject)</li> 
<li>[2.3 Quay trở lại một thư mục hoặc tập tin](#gobackdirectory)</li> 
<li>[2.4 Xem những gì có trong thư mục của bạn](#viewdirectory)</li> 
<li>[2.5 Tạo một thư mục](#createdirectory)</li> 
<li>[2.6 Tạo một README. md hoặc tập tin trong thư mục](#createREADME.md)</li> 
<li>[2.7 Xóa một tập tin](#removefile)</li> 
<li>[2.8 Xóa một thư mục và tất cả các nội dung của nó](#removedirectory)</li> 
<li>[2.9 Xem lịch sử trong dòng lệnh](#viewhistory)</li>
<li>[2.10 Thực hiện lệnh mà tài khoản bạn đang sử dụng thiếu quyền](#carryoutcommand)</li>
<li>[2.11 Nói cho bạn đang ở đâu](#Tell)</li>
</ul>

<a name="startworking"></a>
###1. Bắt đầu làm việc với các project
Trong Git, khi bạn sao chép một dự án, bạn nói rằng bạn 'bản sao' nó. Để làm việc trên một dự án git tại địa phương (từ máy tính của bạn), bạn sẽ cần phải sao chép nó. Để làm điều này, đăng nhập vào GitLab. 

Khi bạn đang trên Bảng điều khiển của bạn, nhấp chuột vào dự án mà bạn muốn sao chép. Để làm việc trong dự án, bạn có thể sao chép một liên kết đến các kho Git thông qua một SSH hoặc một giao thức HTTPS. SSH là dễ dàng hơn để sử dụng sau khi nó được thiết lập. Trong khi bạn đang ở tab Project, chọn HTTPS hoặc SSH từ trình đơn thả xuống và sao chép liên kết bằng cách sử dụng 'Copy to clipboard' nút (bạn sẽ phải dán trên vỏ của bạn trong bước tiếp theo).

<a name="commandline"></a>
###2. Trên giao diện dòng lệnh
<a name="cloneproject"></a>
####2.1 Clone dự án của bạn
Tới vỏ của máy tính của bạn và gõ lệnh sau đây:
```
git clone PASTE HTTPS OR SSH HERE
```
Một bản sao của dự án sẽ được tạo ra trong máy tính của bạn.
<a name="gointoproject"></a>
####2.2 Đi vào một project, thư mục hoặc tập tin để làm việc trong đó
```
cd NAME-OF-PROJECT-OR-FILE
```
<a name="gobackdirectory"></a>
####2.3 Quay trở lại một thư mục hoặc tập tin
```
cd ../
```
<a name="viewdirectory"></a>
####2.4 Xem những gì có trong thư mục của bạn
```
ls
```
<a name="createdirectory"></a>
####2.5 Tạo một thư mục
```
mkdir NAME-OF-YOUR-DIRECTORY
```
<a name="createREADME.md"></a>
####2.6 Tạo một README. md hoặc tập tin trong thư mục
```
touch README.md
nano README.md
#### ADD YOUR INFORMATION
#### Press: control + X
#### Type: Y
#### Press: enter
```
<a name="removefile"></a>
####2.7 Xóa một tập tin
```
rm NAME-OF-FILE
```
<a name="#removedfirectory"></a>
####2.8 Xóa một thư mục và tất cả các nội dung của nó
```
rm -rf NAME-OF-DIRECTORY
```
<a name="viewhistory"></a>
####2.9 Xem lịch sử trong dòng lệnh
```
history
```
<a name="caryoutcommand"></a>
####2.10 Thực hiện lệnh mà tài khoản bạn đang sử dụng thiếu quyền
Bạn sẽ được yêu cầu nhập mật khẩu của người quản trị.
```
sudo
```
<a name="Tell"></a>
####2.11 Nói cho bạn đang ở đâu
```
pwd
```
