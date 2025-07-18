Không thể truy cập mail qua client (IMAP/POP3)

## **Không thể truy cập mail qua client (IMAP/POP3)**

**Nguyên nhân:**

- Cổng IMAP/POP3 chưa mở trong firewall.
    
- Cấu hình Dovecot chưa chính xác.
    

**Cách xử lý:**

- Kiểm tra IMAP:
    
    `dovecot -n | grep imap`
    
- Kiểm tra firewall:
    
    `firewall-cmd --add-port=143/tcp --permanentfirewall-cmd --add-port=993/tcp --permanentfirewall-cmd --reload`

id: e9f07c3369044b1d9432df4cfe1847c1
parent_id: bc33dce65848438199af0fd3912185dd
created_time: 2025-04-22T09:43:10.018Z
updated_time: 2025-04-23T07:36:48.313Z
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
user_created_time: 2025-04-22T09:43:10.018Z
user_updated_time: 2025-04-23T07:36:48.313Z
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