Cài Docker AlmaLinux

### Bước 1: Cập nhật hệ thống

Trước tiên, hãy chắc chắn rằng hệ thống của bạn đã được cập nhật:

`sudo dnf update -y`

### Bước 2: Cài đặt các gói cần thiết

Cài đặt một số gói phụ trợ cần thiết để Docker có thể hoạt động:

`sudo dnf install -y yum-utils`

### Bước 3: Thêm kho Docker vào hệ thống

Docker không có sẵn trong kho chính thức của AlmaLinux, vì vậy bạn cần thêm kho Docker:

`sudo dnf config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo`

### Bước 4: Cài đặt Docker

Bây giờ bạn có thể cài đặt Docker:

`sudo dnf install -y docker-ce docker-ce-cli containerd.io`

### Bước 5: Khởi động và kích hoạt Docker

Sau khi cài đặt xong, bạn cần khởi động dịch vụ Docker và đảm bảo nó tự khởi động cùng hệ thống:

`sudo systemctl start dockersudo systemctl enable docker`

### Bước 6: Kiểm tra cài đặt

Cuối cùng, kiểm tra xem Docker đã cài đặt thành công hay chưa bằng cách chạy lệnh:

`docker --version`

Nếu bạn nhận được thông tin phiên bản Docker, nghĩa là Docker đã được cài đặt thành công.

### Bước 7: Thêm người dùng vào nhóm Docker (tùy chọn)

Nếu bạn muốn chạy Docker mà không cần quyền `sudo`, hãy thêm người dùng của bạn vào nhóm Docker:

`sudo usermod -aG docker $USER`

Để thay đổi có hiệu lực, bạn có thể đăng xuất và đăng nhập lại, hoặc sử dụng lệnh sau:

`newgrp docker`

Sau khi thực hiện các bước trên, Docker sẽ được cài đặt và chạy trên hệ thống AlmaLinux của bạn!

id: 6b07fe631a924b93873eedd018906418
parent_id: bc33dce65848438199af0fd3912185dd
created_time: 2025-04-16T07:33:36.848Z
updated_time: 2025-04-23T07:13:16.743Z
is_conflict: 0
latitude: 21.02776440
longitude: 105.83415980
altitude: 0.0000
author: 
source_url: 
is_todo: 0
todo_due: 0
todo_completed: 0
source: joplin-desktop
source_application: net.cozic.joplin-desktop
application_data: 
order: 0
user_created_time: 2025-04-16T07:33:36.848Z
user_updated_time: 2025-04-23T07:13:16.743Z
encryption_cipher_text: 
encryption_applied: 0
markup_language: 1
is_shared: 0
share_id: 
conflict_original_id: 
master_key_id: 
user_data: 
deleted_time: 0
type_: 1