Lỗi session / login loop

## **Lỗi session / login loop**

**Nguyên nhân:**

- PHP không ghi được session.
    
- Thiếu quyền thư mục `/var/lib/php/session` hoặc tương đương.
    

**Cách khắc phục:**

- Sửa quyền:
    
    `chown -R apache:apache /var/lib/php/sessionchmod 700 /var/lib/php/session`
    
- Kiểm tra `php.ini`:
    
    ini
    
    `session.save_path = "/var/lib/php/session"`

id: a80a6512389949f6989804f27ae19cc2
parent_id: bc33dce65848438199af0fd3912185dd
created_time: 2025-04-22T09:28:43.924Z
updated_time: 2025-04-23T07:25:48.658Z
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
user_created_time: 2025-04-22T09:28:43.924Z
user_updated_time: 2025-04-23T07:25:48.658Z
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