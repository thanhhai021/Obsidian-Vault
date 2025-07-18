Lỗi certificate khi mail client kết nối (SSL handshake failed)

## **Lỗi certificate khi mail client kết nối (SSL handshake failed)**

**Nguyên nhân:**

- Let’s Encrypt hết hạn.
    
- Không cấu hình đúng `ssl_cert` và `ssl_key` trong Dovecot/Postfix.
    

**Cách xử lý:**

`# Dovecot:ssl_cert = </etc/letsencrypt/live/domain.com/fullchain.pemssl_key = </etc/letsencrypt/live/domain.com/privkey.pem# Postfix:smtpd_tls_cert_file = /etc/letsencrypt/live/domain.com/fullchain.pemsmtpd_tls_key_file = /etc/letsencrypt/live/domain.com/privkey.pem# Sau đó restart dịch vụ`

id: b78832e252754bc784e6b1e7571580f0
parent_id: bc33dce65848438199af0fd3912185dd
created_time: 2025-04-22T09:38:32.740Z
updated_time: 2025-04-23T07:36:27.413Z
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
user_created_time: 2025-04-22T09:38:32.740Z
user_updated_time: 2025-04-23T07:36:27.413Z
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