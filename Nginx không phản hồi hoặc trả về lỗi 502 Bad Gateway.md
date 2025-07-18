Nginx không phản hồi hoặc trả về lỗi 502 Bad Gateway

## **Nginx không phản hồi hoặc trả về lỗi 502 Bad Gateway**

**Nguyên nhân:**

- Proxy backend (Apache, PHP-FPM) không chạy.
    
- Cấu hình không đúng trong `nginx.conf`.
    

**Cách xử lý:**

- Kiểm tra xem PHP-FPM hoặc Apache có chạy không:
    
    `systemctl status php-fpmsystemctl status apache2`
    
- Nếu sử dụng PHP-FPM, kiểm tra xem Nginx có đang chuyển tiếp đúng đến PHP-FPM:
    
    `location ~ \.php$ { fastcgi_pass unix:/var/run/php/php7.4-fpm.sock; fastcgi_param SCRIPT_FILENAME /var/www/html$fastcgi_script_name;}`
    
- Kiểm tra log lỗi Nginx:
    
    `tail -f /var/log/nginx/error.log`

id: 717f454771634d53bcb2569e00a88109
parent_id: bc33dce65848438199af0fd3912185dd
created_time: 2025-04-22T09:45:08.869Z
updated_time: 2025-04-23T07:35:44.156Z
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
user_created_time: 2025-04-22T09:45:08.869Z
user_updated_time: 2025-04-23T07:35:44.156Z
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