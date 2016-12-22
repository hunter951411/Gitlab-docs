##GitLab Container Registry

- [1. GitLab Container Registry](#GitLabContainerRegistry)
- [2. Enable the Container Registry for your project(Bật Docker Registry cho project của bạn)](#EnableContainerRegistry)
- [3. Build and push images(Tạo và đẩy images)](#BuildAndPushImages)
- [4. Use images from GitLab Container Registry(Sử dụng images từ GitLab Container Registry)](#UseImages)
- [5. Control Container Registry from within GitLab(Điều khiển Container Registry từ GitLab)](#ControlContainer)
- [6. Build and push images using GitLab CI(Tạo và đẩy Images sử dụng GitLab CI)](#BuildAndPushGitLabCI)
- [7. Limitations(Hạn chế)](#Limitations)
- [8. Troubleshooting the GitLab Container Registry(Xử lý GitLab Container Registry)](#Troubleshooting)
<ul>
<li>[8.1. Basic Troubleshooting(Sửa cơ bản)](#Basic)</li>
<li>[8.2. Advanced Troubleshooting(Sửa nâng cao)](#Advanced)</li>
<li>
<ul>
<li>[8.2.1. Unexpected 403 error during push(Lỗi 403 trong quá trình push)](#Unexpected403)</li>
<li>[8.2.2. mitmproxy](#mitmproxy)</li>
<li>[8.2.3. Running the Docker daemon with a proxy(Chạy tiến trình Docker với một proxy)](#DockerDaemon)</li>
<li>[8.2.4. Running the Docker client(Chạy Docker Client)](#DockerClient)</li>
</ul></li>
</ul>

<a name="GitLabContainerRegistry"></a>
###1. GitLab Container Registry
```
Giới thiệu trong GitLab 8.8
```
```
Lưu ý:
Docker Registry hỗ trợ manifest v1 đã được thêm vào trong GitLab 8.9 để hỗ trợ các phiên bản Docker sớm hơn 1.10 
Tài liệu này là về các hướng dẫn sử dụng. Để tìm hiểu làm thế nào để kích hoạt tính năng GitLab container Registry trên GitLab của bạn, hãy truy cập các tài liệu hướng dẫn quản trị viên. 
Bắt đầu từ GitLab 8. 12, nếu bạn đã kích hoạt 2FA trong tài khoản của bạn, bạn cần phải vượt qua một truy cập Token cá nhân thay vì mật khẩu của bạn để đăng nhập vào container Registry GitLab.
```
Với tích hợp các Docker container Registry vào GitLab, mỗi dự án có thể có không gian riêng của mình để lưu trữ Docker images. 

Bạn có thể đọc thêm về Docker Registry tại https://docs.docker.com/registry/introduction/

<a name="EnableContainerRegistry"></a>
###2. Bật Docker Registry cho project của bạn
Thứ nhất, yêu cầu quản trị hệ thống của bạn để cho phép GitLab container Registry sau đây các tài liệu hành chính. Nếu bạn đang sử dụng GitLab.com, điều này được kích hoạt mặc định, do đó bạn có thể bắt đầu bằng cách sử dụng Registry ngay lập tức. 

Vào cài đặt của dự án của bạn và kích hoạt tính năng container Registry trên dự án của bạn. Đối với dự án mới này có thể được kích hoạt theo mặc định. Đối với dự án có sẵn (trước GitLab 8.8), bạn sẽ phải kích hoạt nó một cách rõ ràng.

<a name="BuildAndPushImages"></a>
###3. Tạo và đẩy images
<a name="UseImages"></a>
###4. Sử dụng images từ GitLab Container Registry
<a name="ControlContainer"></a>
###5. Điều khiển Container Registry từ GitLab
<a name="BuildAndPushGitLabCI"></a>
###6. Tạo và đẩy Images sử dụng GitLab CI
<a name="Limitations"></a>
###7. Hạn chế
<a name="Troubleshooting"></a>
###8. Xử lý GitLab Container Registry
<a name="Basic"></a>
####8.1. Sửa cơ bản
<a name="Advanced"></a>
####8.2. Sửa nâng cao
<a name="Unexpected403"></a>
####8.2.1. Lỗi 403 trong quá trình push
<a name="mitmproxy"></a>
####8.2.2. mitmproxy
<a name="DockerDaemon"></a>
####8.2.3. Chạy tiến trình Docker với một proxy
<a name="DockerClient"></a>
####8.2.4. Chạy Docker Client
