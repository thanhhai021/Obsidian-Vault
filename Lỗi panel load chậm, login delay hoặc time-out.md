Lỗi panel load chậm, login delay hoặc time-out

## **Lỗi panel load chậm, login delay hoặc time-out**

**Nguyên nhân:**

- DNS không resolve đúng.
    
- Bị treo truy vấn MySQL hoặc quota disk.
    

**Cách xử lý:**

- Thêm DNS vào `/etc/resolv.conf`:
    
    &nbsp;
    
    `nameserver 1.1.1.1nameserver 8.8.8.8`
    
- Kiểm tra truy vấn treo:
    
    `mysqladmin processlist`

id: daf819f736334631ae76ad8a5d8579e0
parent_id: bc33dce65848438199af0fd3912185dd
created_time: 2025-04-22T09:35:42.159Z
updated_time: 2025-04-23T07:36:05.717Z
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
user_created_time: 2025-04-22T09:35:42.159Z
user_updated_time: 2025-04-23T07:36:05.717Z
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