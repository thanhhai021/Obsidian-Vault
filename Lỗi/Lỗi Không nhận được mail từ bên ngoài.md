Không nhận được mail từ bên ngoài

## **Không nhận được mail từ bên ngoài**

**Nguyên nhân:**

- Port 25 bị chặn (do nhà mạng hoặc firewall).
    
- Chưa cấu hình MX record đúng.
    
- Postfix không nghe trên đúng IP/domain.
    

**Cách xử lý:**

`# Kiểm tra MX:dig MX yourdomain.com# Mở port:firewall-cmd --add-port=25/tcp --permanentfirewall-cmd --reload`

id: bbafe253d5b1450788814b86f88555c5
parent_id: bc33dce65848438199af0fd3912185dd
created_time: 2025-04-22T09:37:33.851Z
updated_time: 2025-04-23T07:36:54.543Z
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
user_created_time: 2025-04-22T09:37:33.851Z
user_updated_time: 2025-04-23T07:36:54.543Z
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