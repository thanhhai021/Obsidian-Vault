Lỗi không tạo được database/user trong panel (MySQL)

## **Lỗi không tạo được database/user trong panel (MySQL)**

**Nguyên nhân:**

- MySQL không chạy.
    
- Thiếu quyền file trong `/var/lib/mysql`.
    

**Cách xử lý:**

bash

CopyEdit

`systemctl restart mysqldchown -R mysql:mysql /var/lib/mysqlrestorecon -Rv /var/lib/mysql # nếu có SELinux`

id: 40847f97b095423899c37400a10e3ca7
parent_id: bc33dce65848438199af0fd3912185dd
created_time: 2025-04-22T09:30:08.319Z
updated_time: 2025-04-23T07:36:15.571Z
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
user_created_time: 2025-04-22T09:30:08.319Z
user_updated_time: 2025-04-23T07:36:15.571Z
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