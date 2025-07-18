Mail gửi bị trả lại – “blocked” / IP bị blacklist

## **Mail gửi bị trả lại – “blocked” / IP bị blacklist**

**Nguyên nhân:**

- IP server nằm trong blacklist (Spamhaus, Barracuda...).
    
- Không có PTR record.
    

**Cách xử lý:**

- Kiểm tra blacklist:  
    https://mxtoolbox.com/blacklists.aspx
    
- Thêm PTR record (nếu có quyền DNS ngược):
    
    - Ví dụ: `x.x.x.x PTR mail.yourdomain.com`

id: dbf0069e65b74834af0c566d9c3dd288
parent_id: bc33dce65848438199af0fd3912185dd
created_time: 2025-04-22T09:38:17.203Z
updated_time: 2025-04-23T07:35:48.838Z
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
user_created_time: 2025-04-22T09:38:17.203Z
user_updated_time: 2025-04-23T07:35:48.838Z
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