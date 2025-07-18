Lỗi Cloudflare không nhận IP thật (toàn IP Cloudflare)

## **Lỗi Cloudflare không nhận IP thật (toàn IP Cloudflare)**

**Nguyên nhân:**

- Web server không xử lý `CF-Connecting-IP`.

**Cách xử lý:**

- Apache:
    
    `RemoteIPHeader CF-Connecting-IP`
    
- Nginx:
    
    `real_ip_header CF-Connecting-IP;set_real_ip_from 103.21.244.0/22; # và các dải IP khác của CF`

id: d78eb91591a7465cadecf348a5248fbc
parent_id: bc33dce65848438199af0fd3912185dd
created_time: 2025-04-22T09:35:58.055Z
updated_time: 2025-04-23T07:36:24.251Z
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
user_created_time: 2025-04-22T09:35:58.055Z
user_updated_time: 2025-04-23T07:36:24.251Z
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