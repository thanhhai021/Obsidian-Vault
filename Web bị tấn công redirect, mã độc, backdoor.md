Web bị tấn công: redirect, mã độc, backdoor

## **Web bị tấn công: redirect, mã độc, backdoor**

**Dấu hiệu:**

- Web bị redirect về trang lạ.
    
- Google báo website có mã độc.
    
- Xuất hiện file lạ như `wso.php`, `shell.php`...
    

**Cách xử lý:**

- Quét mã độc:
    
    `clamscan -r /var/www/html`
    
- Kiểm tra `.htaccess`, file `functions.php`, file mới tạo gần đây:
    
    &nbsp;
    
    `find /var/www/html -type f -mtime -2`

id: c4f2fbdfb87e4b4eb32b83e2646a0749
parent_id: bc33dce65848438199af0fd3912185dd
created_time: 2025-04-22T09:31:05.176Z
updated_time: 2025-04-23T07:33:25.177Z
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
user_created_time: 2025-04-22T09:31:05.176Z
user_updated_time: 2025-04-23T07:33:25.177Z
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