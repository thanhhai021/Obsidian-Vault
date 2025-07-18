Apache không khởi động được sau khi cấu hình lại

## **Apache không khởi động được sau khi cấu hình lại**

**Nguyên nhân:**

- Cấu hình sai trong file `httpd.conf` hoặc `.htaccess`.
    
- Thiếu module cần thiết.
    

**Cách xử lý:**

- Kiểm tra cấu hình Apache:
    
    &nbsp;
    
    `apachectl configtest`
    
- Nếu có lỗi, Apache sẽ chỉ ra vị trí và loại lỗi.
    
- Đảm bảo các module cần thiết đã được bật, ví dụ:
    
    &nbsp;
    
    &nbsp;
    
    `a2enmod rewrite`
    
- Restart Apache:
    
    &nbsp;
    
    `systemctl restart apache2`

id: 34421dc315f445a5b35590ff5d2d1ebf
parent_id: bc33dce65848438199af0fd3912185dd
created_time: 2025-04-22T09:45:06.182Z
updated_time: 2025-04-23T07:11:46.657Z
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
user_created_time: 2025-04-22T09:45:06.182Z
user_updated_time: 2025-04-23T07:11:46.657Z
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