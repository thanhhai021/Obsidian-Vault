Cài my sql

Cài my sql

Cài my sql  
 wget http://dev.mysql.com/get/mysql57-community-release-el7-9.noarch.rpm  
 sudo systemctl start mysqld  
 sudo systemctl status mysqld  
 xem mật khẩu sql sudo grep 'password' /var/log/mysqld.log  
 sudo mysql_secure_installation  
 sudo mysqld_safe --skip-grant-tables reset pass  
 mysql -uroot

&nbsp;----------------------------------------------------------------  
Để đổi mật khẩu root, nhập lệnh sau:  
USE MYSQL;  
UPDATE USER SET PASSWORD=PASSWORD(“newpassword”) WHERE USER=’root’;  
FLUSH PRIVILEGES;  
EXIT  
Thay thế newpassword với mật khẩu mạnh của riêng bạn.  
Cuối cùng, khởi động lại MySQL bằng lệnh;  
sudo systemctl start mysqld  
Bạn có thể đăng nhập vào MySQL bằng mật khẩu mới.  
Tạo mới MySQL User, Database  
Là user root trong MySQL, bạn có toàn quyền truy cập vào mọi database.

  
Đây là cách tạo database, user MySQL mới:

Sử dụng lệnh sau để tạo mới database:  
CREATE DATABASE newdb  
Đổi newdb bằng tên database của bạn.  
Tạo user mới bằng cách gõ vào dòng sau:  
CREATE USER 'username'@'localhost' IDENTIFIED BY 'password'  
Đổi biến cho cả username và password để tạo user mới.  
Nếu bạnm muốn xóa một user nhất định, dùng lệnh sau:  
DROP USER ‘username’@‘localhost’  
Quản lý MySQL User Permissions (quyền thao tác của MySQL user)  
Gán quyền truy cập vào database cho user mới bằng lệnh sau:  
<br/>

id: 28039318a0244c128ed71f701e3144f3
parent_id: bc33dce65848438199af0fd3912185dd
created_time: 2025-04-15T07:00:02.367Z
updated_time: 2025-04-15T08:54:28.684Z
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
user_created_time: 2025-04-15T07:00:02.367Z
user_updated_time: 2025-04-15T07:01:23.286Z
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