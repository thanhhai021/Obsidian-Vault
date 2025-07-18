Tường lửa (Firewall) không cho phép kết nối từ ngoài

## **Tường lửa (Firewall) không cho phép kết nối từ ngoài**

**Nguyên nhân:**

- Tường lửa chưa mở port (SMTP, IMAP, HTTP).
    
- Các kết nối mạng từ bên ngoài bị chặn.
    

**Cách xử lý:**

- Mở port cần thiết:
    
    &nbsp;
    
    `firewall-cmd --add-port=25/tcp --permanentfirewall-cmd --add-port=587/tcp --permanentfirewall-cmd --add-port=993/tcp --permanentfirewall-cmd --reload`

id: 27a66cb7a27842a7a2ca9029e2b9b19b
parent_id: bc33dce65848438199af0fd3912185dd
created_time: 2025-04-22T09:42:26.571Z
updated_time: 2025-04-23T07:34:48.363Z
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
user_created_time: 2025-04-22T09:42:26.571Z
user_updated_time: 2025-04-23T07:34:48.363Z
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