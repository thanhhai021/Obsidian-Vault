Cài lavarel Script

#!/bin/bash

\# Cài đặt các gói cần thiết  
dnf install -y epel-release  
dnf install -y https://rpms.remirepo.net/enterprise/remi-release-10.rpm  
dnf module enable -y php:remi-8.2  
dnf install -y php php-cli php-common php-mbstring php-xml php-bcmath php-curl php-mysqlnd php-zip unzip curl git httpd mariadb-server policycoreutils-python-utils

\# Cài đặt Node.js và npm  
curl -sL https://rpm.nodesource.com/setup_18.x | bash -  
dnf install -y nodejs

\# Khởi động và bật các dịch vụ cần thiết  
systemctl enable --now httpd mariadb

\# Cài đặt Composer  
curl -sS https://getcomposer.org/installer | php && mv composer.phar /usr/local/bin/composer

\# Cài đặt Laravel  
composer global require laravel/installer  
export PATH="$HOME/.config/composer/vendor/bin:$PATH"  
echo 'export PATH="$HOME/.config/composer/vendor/bin:$PATH"' >> ~/.bashrc  
source ~/.bashrc

\# Tạo database và user cho Laravel  
mysql -u root <<EOF  
CREATE DATABASE laravel;  
CREATE USER 'laraveluser'@'localhost' IDENTIFIED BY 'matkhau123';  
GRANT ALL PRIVILEGES ON laravel.\* TO 'laraveluser'@'localhost';  
FLUSH PRIVILEGES;  
EOF

\# Tạo Laravel project  
mkdir -p /var/www  
cd /var/www && ~/.config/composer/vendor/bin/laravel new laravelapp  
chown -R apache:apache /var/www/laravelapp  
chmod -R 755 /var/www/laravelapp

\# Cập nhật file .env cho Laravel với thông tin database  
sed -i 's/DB_DATABASE=.\*/DB_DATABASE=laravel/' /var/www/laravelapp/.env  
sed -i 's/DB_USERNAME=.\*/DB_USERNAME=laraveluser/' /var/www/laravelapp/.env  
sed -i 's/DB_PASSWORD=.\*/DB_PASSWORD=matkhau123/' /var/www/laravelapp/.env

\# Cài đặt các thư viện frontend và build với npm  
cd /var/www/laravelapp  
npm install  
npm run build

\# Cấu hình Apache VirtualHost cho Laravel  
cat > /etc/httpd/conf.d/laravelapp.conf <<EOF  
&lt;VirtualHost \*:80&gt;  
    ServerName localhost  
    DocumentRoot /var/www/laravelapp/public  
    &lt;Directory /var/www/laravelapp&gt;  
        AllowOverride All  
        Require all granted  
    &lt;/Directory&gt;  
&lt;/VirtualHost&gt;  
EOF

\# Cấu hình SELinux cho phép Apache kết nối DB  
setsebool -P httpd_can_network_connect_db 1  
setsebool -P httpd_execmem 1  
chcon -R -t httpd_sys_rw_content_t /var/www/laravelapp

\# Khởi động lại Apache  
systemctl restart httpd

\# Migrate database để tạo các bảng  
cd /var/www/laravelapp  
php artisan migrate

echo "Laravel đã được cài đặt và cấu hình thành công!"

id: dfd061fb754148fd8535388eaf35329c
parent_id: bc33dce65848438199af0fd3912185dd
created_time: 2025-05-09T08:27:52.246Z
updated_time: 2025-05-09T08:28:12.856Z
is_conflict: 0
latitude: 10.82309890
longitude: 106.62966380
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
user_created_time: 2025-05-09T08:27:52.246Z
user_updated_time: 2025-05-09T08:28:12.856Z
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