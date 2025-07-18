Dovecot không hoạt động – không kết nối được IMAP/POP3**

## **Dovecot không hoạt động – không kết nối được IMAP/POP3**

**Triệu chứng:**

- Mail client không sync inbox.
    
- Port 143/993 không kết nối được.
    

**Nguyên nhân:**

- Dovecot chưa chạy.
    
- SSL cert sai đường dẫn hoặc expired.
    

**Cách xử lý:**

`systemctl restart dovecot# Kiểm tra log:journalctl -xeu dovecot`

id: 586a7b996fcc44dbbecee4ce3c081606
parent_id: bc33dce65848438199af0fd3912185dd
created_time: 2025-04-22T09:37:37.562Z
updated_time: 2025-04-23T07:19:17.656Z
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
user_created_time: 2025-04-22T09:37:37.562Z
user_updated_time: 2025-04-23T07:19:17.656Z
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