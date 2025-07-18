Lỗi SSL không hợp lệ dù đã cài Let's Encrypt

## **Lỗi SSL không hợp lệ dù đã cài Let's Encrypt**

**Nguyên nhân:**

- Trình duyệt báo thiếu chain certificate.
    
- Cài thiếu fullchain.pem.
    

**Cách xử lý:**

- Với Apache:
    
    `SSLCertificateFile /etc/letsencrypt/live/yourdomain.com/fullchain.pemSSLCertificateKeyFile /etc/letsencrypt/live/yourdomain.com/privkey.pem`
    
- Kiểm tra bằng:  
    https://www.sslshopper.com/ssl-checker.html

id: b4adebd3f88e4b77982ac1c08dc55d66
parent_id: bc33dce65848438199af0fd3912185dd
created_time: 2025-04-22T09:33:45.164Z
updated_time: 2025-04-23T07:26:02.437Z
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
user_created_time: 2025-04-22T09:33:45.164Z
user_updated_time: 2025-04-23T07:26:02.437Z
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