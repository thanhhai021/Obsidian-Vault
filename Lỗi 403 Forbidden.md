Lỗi 403 Forbidden

## Lỗi 403 Forbidden

Nguyên nhân:

- Sai permission (quyền truy cập file/folder).
    
- File `.htaccess` chặn quyền truy cập.
    
- Thiếu file `index`.
    

Cách khắc phục:

- Chmod thư mục: `chmod 755 /path/to/folder`
    
- Chmod file: `chmod 644 /path/to/file`
    
- Kiểm tra `.htaccess`: comment các dòng liên quan tới `deny`, `Require all denied`, v.v.
    
- Đảm bảo thư mục có file `index.html`, `index.php`...

id: 007afa77c8fb410caab6c6551d639d6c
parent_id: bc33dce65848438199af0fd3912185dd
created_time: 2025-04-22T09:22:31.659Z
updated_time: 2025-04-22T09:22:54.492Z
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
user_created_time: 2025-04-22T09:22:31.659Z
user_updated_time: 2025-04-22T09:22:54.492Z
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