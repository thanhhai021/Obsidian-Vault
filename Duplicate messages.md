Quá nhiều bản sao (duplicate messages) trong mail queue

## **Quá nhiều bản sao (duplicate messages) trong mail queue**

**Nguyên nhân:**

- Mail server cố gắng gửi lại quá nhiều lần.
    
- Quá tải trong mail queue.
    

**Cách xử lý:**

- Kiểm tra mail queue:
    
    &nbsp;
    
    `mailq`
    
- Xoá các email bị lỗi trong queue:
    
    &nbsp;
    
    `postsuper -d ALL`

id: 5ef269a9914644e8820d4675ca34307d
parent_id: bc33dce65848438199af0fd3912185dd
created_time: 2025-04-22T09:42:55.498Z
updated_time: 2025-04-23T07:35:24.181Z
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
user_created_time: 2025-04-22T09:42:55.498Z
user_updated_time: 2025-04-23T07:35:24.181Z
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