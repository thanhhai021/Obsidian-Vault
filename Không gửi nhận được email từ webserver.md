Không gửi/nhận được email từ webserver

## **Không gửi/nhận được email từ webserver**

**Nguyên nhân:**

- Port mail bị chặn (25, 465, 587).
    
- Webserver chưa cấu hình mail (SMTP).
    
- DKIM/SPF chưa cấu hình đúng.
    

**Cách khắc phục:**

- Mở port trong firewall hoặc yêu cầu ISP mở port 25.
    
- Cấu hình SMTP trong CMS như WordPress bằng plugin như WP Mail SMTP.
    
- Cấu hình SPF/DKIM/DMARC cho domain.

id: 2c3cfa5b3ee244509b970524415b78cc
parent_id: bc33dce65848438199af0fd3912185dd
created_time: 2025-04-22T09:25:02.855Z
updated_time: 2025-04-22T09:25:19.871Z
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
user_created_time: 2025-04-22T09:25:02.855Z
user_updated_time: 2025-04-22T09:25:19.871Z
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