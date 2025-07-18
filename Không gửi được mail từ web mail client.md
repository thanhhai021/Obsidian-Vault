Không gửi được mail từ web mail client

## **Không gửi được mail từ web/mail client**

**Triệu chứng:**

- SMTP timeout.
    
- Web form báo “Could not send email”.
    
- Mail client báo lỗi 550/553.
    

**Nguyên nhân:**

- Chưa mở port 587 hoặc 465 (SMTP).
    
- Chưa cấu hình relay / TLS đúng.
    
- Web server gửi mail không có `From` hợp lệ.
    

**Cách xử lý:**

`firewall-cmd --add-port=587/tcp --permanentfirewall-cmd --reload# Kiểm tra cấu hình SMTP:postconf | grep relayhost`

id: 5e955dae3ea54518a069fae94c9c3c70
parent_id: bc33dce65848438199af0fd3912185dd
created_time: 2025-04-22T09:36:48.128Z
updated_time: 2025-04-23T07:37:43.499Z
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
user_created_time: 2025-04-22T09:36:48.128Z
user_updated_time: 2025-04-23T07:37:43.499Z
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