OpenSSL

### 1\. **Tạo chứng chỉ SSL tự ký (self-signed certificate)**

bash

CopyEdit

`openssl req -x509 -newkey rsa:2048 -keyout key.pem -out cert.pem -days 365 -nodes`

- `key.pem`: private key.
    
- `cert.pem`: chứng chỉ SSL.
    
- `-nodes`: không mã hóa private key.
    

* * *

### 2\. **Tạo CSR (Certificate Signing Request) để xin SSL từ CA**

bash

CopyEdit

`openssl req -new -newkey rsa:2048 -nodes -keyout domain.key -out domain.csr`

- `domain.key`: file chứa private key.
    
- `domain.csr`: file CSR gửi cho CA để cấp chứng chỉ.
    

* * *

### 3\. **Kiểm tra thông tin một chứng chỉ SSL có sẵn**

bash

CopyEdit

`openssl x509 -in cert.pem -text -noout`

* * *

### 4\. **Lấy chứng chỉ SSL từ máy chủ (như khi muốn kiểm tra domain đã cài SSL chưa)**

bash

CopyEdit

`openssl s_client -connect example.com:443`

> Gõ `QUIT` để thoát sau khi hiện chứng chỉ.

* * *

### 5\. **Lưu chứng chỉ từ máy chủ về file**

bash

CopyEdit

`openssl s_client -connect example.com:443 -servername example.com </dev/null | \ sed -n '/-----BEGIN CERTIFICATE-----/,/-----END CERTIFICATE-----/p' > saved_cert.pem`

id: f43b9ff83202405ea8f9de976f5cfe5e
parent_id: bc33dce65848438199af0fd3912185dd
created_time: 2025-05-05T04:31:06.851Z
updated_time: 2025-05-05T04:31:25.368Z
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
user_created_time: 2025-05-05T04:31:06.851Z
user_updated_time: 2025-05-05T04:31:25.368Z
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