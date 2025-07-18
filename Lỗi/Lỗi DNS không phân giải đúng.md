DNS không phân giải đúng

## **DNS không phân giải đúng**

**Nguyên nhân:**

- Thiếu A record, CNAME.
    
- DNS propagation chưa xong.
    
- Domain chưa trỏ về IP.
    

**Cách khắc phục:**

- Dùng `dig`, `nslookup`, `host` để kiểm tra:
    
    &nbsp;
    
    `dig tenmien.com +short`
    
- Kiểm tra DNS Zone trong control panel.
    
- Xóa cache DNS cục bộ:  
    Trên Linux: `systemd-resolve --flush-caches`  
    Trên Windows: `ipconfig /flushdns`

id: 0b1cf81b0c86464ba801e1d544c5abe5
parent_id: bc33dce65848438199af0fd3912185dd
created_time: 2025-04-22T09:26:50.730Z
updated_time: 2025-04-23T07:19:08.547Z
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
user_created_time: 2025-04-22T09:26:50.730Z
user_updated_time: 2025-04-23T07:19:08.547Z
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