Không restore được backup (permission denied hoặc sai owner)

## **Không restore được backup (permission denied hoặc sai owner)**

**Nguyên nhân:**

- File restore không có quyền ghi/thực thi.
    
- Không khớp user giữa hệ thống và file backup.
    

**Cách xử lý:**

`chown -R user:user /home/user/restorecon -Rv /home/user/ # nếu có SELinux`

id: abf049dbcb4f4625a1d8eca270ba2285
parent_id: bc33dce65848438199af0fd3912185dd
created_time: 2025-04-22T09:35:00.590Z
updated_time: 2025-04-23T07:36:51.333Z
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
user_created_time: 2025-04-22T09:35:00.590Z
user_updated_time: 2025-04-23T07:36:51.333Z
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