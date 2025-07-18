Lỗi Mail Server bị DDoS – Gửi quá nhiều mail

## **Lỗi Mail Server bị DDoS – Gửi quá nhiều mail**

**Nguyên nhân:**

- Server bị tấn công DDoS, gửi hàng nghìn email/phút.
    
- Địa chỉ IP server bị flood.
    

**Cách xử lý:**

- Thêm firewall rate-limiting:
    
    &nbsp;
    
    `iptables -A INPUT -p tcp --dport 25 -m limit --limit 10/minute -j ACCEPT`
    
- Cấu hình Postfix hạn chế số lượng email gửi mỗi ngày:
    
    &nbsp;
    
    `smtpd_client_connection_count_limit = 10smtpd_client_connection_rate_limit = 20`

id: 73a6f397382042b5858489dec5ffae49
parent_id: bc33dce65848438199af0fd3912185dd
created_time: 2025-04-22T09:42:07.185Z
updated_time: 2025-04-23T07:36:08.930Z
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
user_created_time: 2025-04-22T09:42:07.185Z
user_updated_time: 2025-04-23T07:36:08.930Z
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