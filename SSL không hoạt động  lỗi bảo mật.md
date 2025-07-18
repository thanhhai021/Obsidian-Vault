SSL không hoạt động / lỗi bảo mật

## **SSL không hoạt động / lỗi bảo mật**

**Nguyên nhân:**

- Chứng chỉ hết hạn.
    
- Cấu hình sai SSL trong webserver.
    
- Không redirect từ http → https.
    

**Cách khắc phục:**

- Kiểm tra hạn SSL: `openssl x509 -in cert.pem -text -noout`
    
- Cấu hình trong Apache:
    
    apache
    
    CopyEdit
    
    `<VirtualHost *:443> SSLEngine on SSLCertificateFile /path/to/cert.pem SSLCertificateKeyFile /path/to/key.pem</VirtualHost>`
    
- Tạo redirect:  
    Apache: `RewriteRule ^ https://%{HTTP_HOST}%{REQUEST_URI} [L,R=301]`  
    Nginx: `return 301 https://$host$request_uri;`

id: 0be6d3b7cf69465f856d249174ce2b1e
parent_id: bc33dce65848438199af0fd3912185dd
created_time: 2025-04-22T09:24:40.981Z
updated_time: 2025-04-22T09:25:01.220Z
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
user_created_time: 2025-04-22T09:24:40.981Z
user_updated_time: 2025-04-22T09:25:01.220Z
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