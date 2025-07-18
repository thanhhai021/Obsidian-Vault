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

