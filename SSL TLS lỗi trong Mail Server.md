SSL/TLS lỗi trong Mail Server (SSL handshake failed)

## **SSL/TLS lỗi trong Mail Server (SSL handshake failed)**

**Nguyên nhân:**

- Chứng chỉ SSL hết hạn.
    
- Cấu hình sai đường dẫn chứng chỉ trong Postfix/Dovecot.
    

**Cách xử lý:**

- Kiểm tra chứng chỉ:
    
    `openssl s_client -connect mail.yourdomain.com:465`
    
- Cập nhật chứng chỉ:
    
    `systemctl restart postfix dovecot`

id: 8df7b85184814b6d851d8ce251080f2e
parent_id: bc33dce65848438199af0fd3912185dd
created_time: 2025-04-22T09:42:58.002Z
updated_time: 2025-04-23T07:35:12.603Z
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
user_created_time: 2025-04-22T09:42:58.002Z
user_updated_time: 2025-04-23T07:35:12.603Z
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