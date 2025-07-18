Lỗi 404 Not Found

## **Lỗi 404 Not Found**

**Nguyên nhân:**

- File không tồn tại.
    
- Rewrite URL không hoạt động (thiếu mod_rewrite/nginx rule).
    

**Cách khắc phục:**

- Kiểm tra đường dẫn URL đúng chưa.
    
- Apache: bật `mod_rewrite` (`a2enmod rewrite`) và cấu hình lại `.htaccess`.
    
- Nginx: kiểm tra block `location /` có `try_files $uri $uri/ /index.php?$query_string;`

id: 66b701e8071b46ad811de5dde0b3ec80
parent_id: bc33dce65848438199af0fd3912185dd
created_time: 2025-04-22T09:23:36.309Z
updated_time: 2025-04-22T09:23:57.454Z
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
user_created_time: 2025-04-22T09:23:36.309Z
user_updated_time: 2025-04-22T09:23:57.454Z
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