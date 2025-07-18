Cài đặt Nextcloud

### 1\. **Cài đặt và chuẩn bị môi trường**

- **Hệ điều hành**: Cài đặt một hệ điều hành Linux (AlmaLinux, CentOS, Ubuntu, v.v.).
    
- **Cài đặt phần mềm cần thiết**:
    
    - **Apache**: `sudo dnf install httpd`
        
    - **PHP**: Cài đặt PHP và các module yêu cầu (PHP 7.4 hoặc mới hơn).
        
    - **MariaDB hoặc MySQL**: Cài đặt MySQL và tạo một cơ sở dữ liệu cho Nextcloud.
        
    - **Redis** (tùy chọn): Dùng Redis để cache và tăng hiệu suất.
        
    - **Mod_php**: Nếu bạn sử dụng Apache.
        

### 2\. **Tải và cài đặt Nextcloud**

- Tải Nextcloud từ trang chính thức:
    
    &nbsp;
    
    `wget https://download.nextcloud.com/server/releases/nextcloud-XX.XX.X.zipunzip nextcloud-XX.XX.X.zipmv nextcloud /var/www/`
    
- **Cấu hình quyền cho thư mục Nextcloud**:
    
    &nbsp;
    
    `chown -R apache:apache /var/www/nextcloudchmod -R 755 /var/www/nextcloud`
    

### 3\. **Cấu hình Apache**

- Tạo một virtual host Apache cho Nextcloud:
    
    &nbsp;
    
    `nano /etc/httpd/conf.d/nextcloud.conf`
    
- Thêm cấu hình virtual host:
    
    &nbsp;
    
    `<VirtualHost *:80> ServerName nexcloud.local DocumentRoot /var/www/nextcloud <Directory /var/www/nextcloud> Options +FollowSymlinks AllowOverride All Require all granted </Directory></VirtualHost>`
    
- **Chạy lại Apache**:
    
    &nbsp;
    
    `systemctl restart httpd`
    

### 4\. **Cài đặt Nextcloud qua Command Line**

- Chạy lệnh để cài đặt Nextcloud:
    
    &nbsp;
    
    `sudo -u apache php /var/www/nextcloud/occ maintenance:install --database "mysql" --database-name "nextcloud" --database-user "nextclouduser" --database-pass "password" --admin-user "admin" --admin-pass "adminpassword" --data-dir "/var/www/nextcloud/data"`
    
    **Lỗi có thể gặp**:
    
    - **Lỗi quyền ghi vào thư mục config hoặc data**:  
        **Fix**: Chạy lệnh `chown` và `chmod` để cấp quyền cho thư mục:
        
        &nbsp;
        
        `chown -R apache:apache /var/www/nextcloudchmod -R 775 /var/www/nextcloud`
        
    - **"Module 'imagick' is already loaded"**:  
        **Fix**: Kiểm tra tệp cấu hình PHP của bạn để loại bỏ việc tải lại module này nếu cần.
        
    - **Lỗi "The Login is already being used"** khi cài đặt:  
        **Fix**: Đảm bảo tài khoản người quản trị chưa được tạo trước đó hoặc xóa cơ sở dữ liệu Nextcloud và bắt đầu lại.
        

### 5\. **Cấu hình "trusted_domains"**

- Nếu bạn gặp lỗi "Access through untrusted domain": **Fix**: Thêm các domain vào tệp `config.php` của Nextcloud:
    
    php
    
    &nbsp;
    
    `'trusted_domains' =>array ( 0 => 'localhost', 1 => 'nexcloud.local', 2 => '192.168.0.15',),`
    
    Cập nhật thông số `overwrite.cli.url`:
    
    php
    
    &nbsp;
    
    `'overwrite.cli.url' => 'http://localhost',`
    

### 6\. **Sửa lỗi "Cannot write into config directory"**

- **Fix**: Cấp quyền cho thư mục `config`:
    
    &nbsp;
    
    `chown -R apache:apache /var/www/nextcloud/configchmod -R 775 /var/www/nextcloud/config`
    
    **Lỗi không thể truy cập thư mục `/var/www/nextcloud/data`**:  
    **Fix**: Tạo thư mục `data` nếu chưa có và cấp quyền:
    
    &nbsp;
    
    `mkdir /var/www/nextcloud/datachown -R apache:apache /var/www/nextcloud/datachmod -R 775 /var/www/nextcloud/data`
    

### 7\. **Khắc phục lỗi "Cannot write into config directory"**

- Nếu Nextcloud không thể ghi vào thư mục `config`, kiểm tra quyền sở hữu và quyền truy cập:
    
    &nbsp;
    
    `chown -R apache:apache /var/www/nextcloud/configchmod -R 775 /var/www/nextcloud/config`
    

### 8\. **Cấu hình SSL (tùy chọn)**

- Nếu bạn muốn sử dụng HTTPS, bạn có thể tạo chứng chỉ SSL tự ký hoặc sử dụng Let's Encrypt:
    
    &nbsp;
    
    `certbot --apache`
    

### 9\. **Các lỗi khác và khắc phục**

- **Lỗi cổng MySQL**: Kiểm tra xem MySQL đang chạy và các cổng cần thiết đã được mở.
    
- **Lỗi cấu hình PHP**: Đảm bảo rằng bạn đã cài đủ các module PHP cần thiết như `php-gd`, `php-imagick`, `php-curl`, `php-xml`, `php-mbstring`.
    

