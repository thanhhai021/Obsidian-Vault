Bị block IP khi login panel nhiều lần sai

## **Bị block IP khi login panel nhiều lần sai**

**Nguyên nhân:**

- CSF, Fail2Ban, hoặc tính năng bảo vệ login.

**Cách xử lý:**

- Gỡ IP khỏi CSF:
    
    &nbsp;
    
    `csf -dr YOUR.IP.ADDRESScsf -tr YOUR.IP.ADDRESS`
    
- Thêm whitelist:
    
    &nbsp;
    
    `csf -a YOUR.IP.ADDRESS`

id: 426ba361ccac43e1aaddbe7ea41d0338
parent_id: bc33dce65848438199af0fd3912185dd
created_time: 2025-04-22T09:32:03.594Z
updated_time: 2025-04-23T07:11:55.077Z
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
user_created_time: 2025-04-22T09:32:03.594Z
user_updated_time: 2025-04-23T07:11:55.077Z
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