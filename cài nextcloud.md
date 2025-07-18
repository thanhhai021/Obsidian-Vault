Script cài nextcloud

script cài nextcloud

#!/bin/bash

\# Cập nhật hệ thống  
dnf -y update

\# Cài Apache, MariaDB, PHP và các extension cần thiết cho Nextcloud  
dnf -y install epel-release  
dnf -y install httpd mariadb-server unzip wget

\# Cài PHP và các extension cần thiết  
dnf module -y reset php  
dnf module -y enable php:8.1  
dnf -y install php php-mysqlnd php-xml php-gd php-mbstring php-curl php-zip php-intl php-bcmath php-imagick php-cli php-common php-opcache php-pecl-apcu php-json

\# Bật và khởi động dịch vụ  
systemctl enable --now httpd mariadb

\# Thiết lập MariaDB  
mysql_secure_installation <<EOF

y  
rootpass  
rootpass  
y  
y  
y  
y  
EOF

\# Tạo database cho Nextcloud  
mysql -uroot -prootpass <<EOF  
CREATE DATABASE nextcloud;  
CREATE USER 'nextclouduser'@'localhost' IDENTIFIED BY 'yourpassword';  
GRANT ALL PRIVILEGES ON nextcloud.\* TO 'nextclouduser'@'localhost';  
FLUSH PRIVILEGES;  
EOF

\# Tải và giải nén Nextcloud  
cd /var/www/  
wget https://download.nextcloud.com/server/releases/latest.zip  
unzip latest.zip  
chown -R apache:apache nextcloud  
chmod -R 755 nextcloud

\# Cấu hình Apache  
cat &lt;<EOL &gt; /etc/httpd/conf.d/nextcloud.conf  
&lt;VirtualHost \*:80&gt;  
    ServerName yourdomain.com

&nbsp;   DocumentRoot /var/www/nextcloud

&nbsp;   &lt;Directory /var/www/nextcloud/&gt;  
        Require all granted  
        AllowOverride All  
        Options FollowSymLinks MultiViews  
    &lt;/Directory&gt;

&nbsp;   ErrorLog /var/log/httpd/nextcloud_error.log  
    CustomLog /var/log/httpd/nextcloud_access.log combined  
&lt;/VirtualHost&gt;  
EOL

\# Mở firewall  
firewall-cmd --permanent --add-service=http  
firewall-cmd --permanent --add-service=https  
firewall-cmd --reload

\# Khởi động lại Apache  
systemctl restart httpd

echo "Cài đặt Nextcloud hoàn tất!"  
echo " Truy cập http://yourdomain.com để tiếp tục cài đặt trên giao diện web."

id: 6c2f4a2a1eb84028bdff77b0f3fec824
parent_id: bc33dce65848438199af0fd3912185dd
created_time: 2025-04-15T07:49:49.044Z
updated_time: 2025-06-16T06:07:51.792Z
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
user_created_time: 2025-04-15T07:49:49.044Z
user_updated_time: 2025-06-16T06:07:51.792Z
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