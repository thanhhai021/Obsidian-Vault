Web bị treo do loop redirect (too many redirects)

## **Web bị treo do loop redirect (too many redirects)**

**Nguyên nhân:**

- `.htaccess` hoặc config web gây redirect lặp.
    
- Dùng HTTPS nhưng không cấu hình đúng (redirect từ HTTP sang HTTPS lặp lại).
    

**Cách xử lý:**

- Kiểm tra `.htaccess`, tạm comment phần redirect.
    
- Nếu dùng proxy/nginx trước Apache, thêm:
    
    `SetEnvIf X-Forwarded-Proto https HTTPS=on`
    
- WordPress: sửa `siteurl`, `home` trong `wp-config.php`.

id: 94bcf257a1c844f3ad7a09daec290965
parent_id: bc33dce65848438199af0fd3912185dd
created_time: 2025-04-22T09:32:56.203Z
updated_time: 2025-04-23T07:34:42.468Z
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
user_created_time: 2025-04-22T09:32:56.203Z
user_updated_time: 2025-04-23T07:34:42.468Z
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