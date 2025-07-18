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


