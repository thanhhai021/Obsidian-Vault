Lỗi không nhận được mail từ một số địa chỉ cụ thể

## **Lỗi không nhận được mail từ một số địa chỉ cụ thể**

**Nguyên nhân:**

- Server gửi không cấu hình đúng rDNS (PTR) hoặc bị blacklist.
    
- Phía gửi không có SPF/DKIM hợp lệ.
    

**Cách xử lý:**

- Kiểm tra PTR:
    
    bash
    
    CopyEdit
    
    `dig -x YOUR.SERVER.IP`
    
- Kiểm tra lại SPF/DKIM của server gửi.

id: b90237a517fb4d57b615778be19db834
parent_id: bc33dce65848438199af0fd3912185dd
created_time: 2025-04-22T09:41:33.759Z
updated_time: 2025-04-23T07:36:17.907Z
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
user_created_time: 2025-04-22T09:41:33.759Z
user_updated_time: 2025-04-23T07:36:17.907Z
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