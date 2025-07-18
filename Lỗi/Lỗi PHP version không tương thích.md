Lỗi PHP version không tương thích

## **Lỗi PHP version không tương thích**

**Nguyên nhân:**

- Web/app yêu cầu PHP phiên bản khác.
    
- Extension PHP bị thiếu (vd: `mysqli`, `curl`, `mbstring`...)
    

**Cách khắc phục:**

- Kiểm tra PHP version: `php -v`
    
- Đổi version nếu dùng nhiều PHP:  
    CyberPanel: qua giao diện > Websites > PHP Version  
    DirectAdmin: `php-selector` hoặc `custombuild`
    
- Cài extension:
    
    `dnf install php-mbstring php-curl php-mysqlnd`

id: 5751bd76537845e5b19c24dea5b94864
parent_id: bc33dce65848438199af0fd3912185dd
created_time: 2025-04-22T09:25:41.456Z
updated_time: 2025-04-23T07:25:26.426Z
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
user_created_time: 2025-04-22T09:25:41.456Z
user_updated_time: 2025-04-23T07:25:26.426Z
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