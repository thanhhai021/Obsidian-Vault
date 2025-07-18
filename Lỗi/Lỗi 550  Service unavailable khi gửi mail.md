Lỗi "550 5.7.1 Service unavailable" khi gửi mail

## **Lỗi "550 5.7.1 Service unavailable" khi gửi mail**

**Nguyên nhân:**

- Mail server từ chối kết nối do chính sách của server nhận.
    
- Thường do IP của bạn bị vào blacklist hoặc SMTP authentication chưa cấu hình đúng.
    

**Cách xử lý:**

- Kiểm tra blacklist IP: https://mxtoolbox.com/blacklists.aspx
    
- Kiểm tra cấu hình SMTP:
    
    `postconf | grep smtpd`

id: 5d508acb557b43a797f8265c404b343d
parent_id: bc33dce65848438199af0fd3912185dd
created_time: 2025-04-22T09:41:01.568Z
updated_time: 2025-04-23T07:36:35.179Z
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
user_created_time: 2025-04-22T09:41:01.568Z
user_updated_time: 2025-04-23T07:36:35.179Z
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