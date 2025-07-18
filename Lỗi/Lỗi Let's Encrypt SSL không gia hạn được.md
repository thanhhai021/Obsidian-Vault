Lỗi Let's Encrypt SSL không gia hạn được

## **Lỗi Let's Encrypt SSL không gia hạn được**

**Nguyên nhân:**

- Domain không trỏ về IP đúng.
    
- Port 80/443 bị chặn.
    
- Có rule `.htaccess` cản `/.well-known/`.
    

**Cách khắc phục:**

- Kiểm tra port:
    
    `nc -zv yourdomain.com 80nc -zv yourdomain.com 443`
    
- Bỏ redirect trong `.htaccess` tạm thời khi renew.
    
- Cập nhật SSL thủ công:
    
    `certbot renew --force-renewal`

id: 9a8fd4d912cd4d25b6ec0303390ab62b
parent_id: bc33dce65848438199af0fd3912185dd
created_time: 2025-04-22T09:28:47.652Z
updated_time: 2025-04-23T07:36:13.202Z
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
user_created_time: 2025-04-22T09:28:47.652Z
user_updated_time: 2025-04-23T07:36:13.202Z
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