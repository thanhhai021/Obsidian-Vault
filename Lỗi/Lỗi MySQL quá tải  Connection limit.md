MySQL quá tải / Connection limit

## **MySQL quá tải / Connection limit**

**Nguyên nhân:**

- Có quá nhiều kết nối đồng thời.
    
- Query chạy chậm, treo.
    

**Cách khắc phục:**

- Tăng giới hạn trong `my.cnf`:
    
    &nbsp;
    
    `max_connections = 300wait_timeout = 60`
    
- Kiểm tra query đang chạy:
    
    &nbsp;
    
    `mysql -e "SHOW PROCESSLIST\G"`
    
- Dọn database bằng `OPTIMIZE TABLE`.

id: 07a440b59ec74cdeb9783f06f9c1775c
parent_id: bc33dce65848438199af0fd3912185dd
created_time: 2025-04-22T09:26:29.209Z
updated_time: 2025-04-23T07:27:59.723Z
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
user_created_time: 2025-04-22T09:26:29.209Z
user_updated_time: 2025-04-23T07:27:59.723Z
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