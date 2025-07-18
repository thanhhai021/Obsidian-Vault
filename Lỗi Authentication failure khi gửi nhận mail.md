Lỗi "Authentication failure" khi gửi/nhận mail

## **Lỗi "Authentication failure" khi gửi/nhận mail**

**Nguyên nhân:**

- Sai thông tin đăng nhập (username/password) trong client.
    
- Không bật xác thực SMTP/IMAP.
    

**Cách xử lý:**

- Kiểm tra lại mật khẩu và cấu hình:
    
    &nbsp;
    
    `postconf -n | grep smtpd_sasldovecot -n | grep auth`
    
- Đảm bảo SMTP/IMAP yêu cầu xác thực đúng:
    
    `smtpd_sasl_auth_enable = yes`

id: 5b2546ceaedc4b10849e3a7c6ba4c4df
parent_id: bc33dce65848438199af0fd3912185dd
created_time: 2025-04-22T09:41:17.799Z
updated_time: 2025-04-23T07:36:32.781Z
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
user_created_time: 2025-04-22T09:41:17.799Z
user_updated_time: 2025-04-23T07:36:32.781Z
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