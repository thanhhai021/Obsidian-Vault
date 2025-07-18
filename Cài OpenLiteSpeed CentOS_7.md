Cài OpenLiteSpeed CentOS_7

### 🚀 **Hướng Dẫn Cài Đặt OpenLiteSpeed**

#### 🔹 **1\. Cài đặt các gói cần thiết và reboot hệ thống**

`sudo yum install epel-release -ysudo yum clean all && sudo yum update -y && sudo shutdown -r now`

Sau khi hệ thống khởi động lại, tiếp tục bước dưới.

* * *

#### 🔹 **2\. Thêm repo của LiteSpeed và cài đặt OpenLiteSpeed**

`sudo rpm -ivh http://rpms.litespeedtech.com/centos/litespeed-repo-1.1-1.el7.noarch.rpmsudo yum install openlitespeed -y`

* * *

#### 🔹 **3\. Cài đặt PHP 7.x (ví dụ PHP 7.1)**

`yum list lsphp* # Xem các phiên bản PHP khả dụng`

Sau đó cài một phiên bản, ví dụ PHP 7.1:

`sudo yum install lsphp71 lsphp71-mysqlnd lsphp71-common lsphp71-gd lsphp71-pdo lsphp71-process lsphp71-mbstring lsphp71-mcrypt lsphp71-opcache lsphp71-bcmath lsphp71-xml -y`

* * *

#### 🔹 **4\. Thiết lập mật khẩu quản trị WebAdmin (port 7080)**

`sudo /usr/local/lsws/admin/misc/admpass.sh`

> Nhập username và password theo yêu cầu (ví dụ: `admin` / `your-secure-password`)

* * *

#### 🔹 **5\. Mở port 7080 để truy cập WebAdmin GUI**

`sudo firewall-cmd --zone=public --permanent --add-port=7080/tcpsudo firewall-cmd --reload`

* * *

#### 🔹 **6\. Truy cập WebAdmin GUI**

Mở trình duyệt và truy cập:

`http://your-server-ip:7080`

Đăng nhập với tài khoản vừa tạo.

id: e550e8a7c119443b8e30ff8d62cc7ab0
parent_id: bc33dce65848438199af0fd3912185dd
created_time: 2025-04-15T07:12:04.678Z
updated_time: 2025-04-23T07:16:08.701Z
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
user_created_time: 2025-04-15T07:12:04.678Z
user_updated_time: 2025-04-23T07:16:08.701Z
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