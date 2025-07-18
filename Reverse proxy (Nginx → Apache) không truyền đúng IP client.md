Reverse proxy (Nginx → Apache) không truyền đúng IP client

## **Reverse proxy (Nginx → Apache) không truyền đúng IP client**

**Nguyên nhân:**

- Apache thấy IP toàn là `127.0.0.1` hoặc `nginx`.

**Cách xử lý:**

- Cài module Apache:
    
    `a2enmod remoteip`
    
- Sửa config:
    
    &nbsp;
    
    `RemoteIPHeader X-Forwarded-For`
    
- Trong Nginx:
    
    &nbsp;
    
    `proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;`

id: fcf6355cb87f4e25b4a9f062072e6b78
parent_id: bc33dce65848438199af0fd3912185dd
created_time: 2025-04-22T09:34:03.629Z
updated_time: 2025-04-23T07:28:43.143Z
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
user_created_time: 2025-04-22T09:34:03.629Z
user_updated_time: 2025-04-23T07:28:43.143Z
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