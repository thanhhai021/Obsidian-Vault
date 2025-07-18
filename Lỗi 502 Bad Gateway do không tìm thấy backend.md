Lỗi "502 Bad Gateway" do không tìm thấy backend

## **Lỗi "502 Bad Gateway" do không tìm thấy backend**

**Nguyên nhân:**

- Nginx không thể kết nối với backend server (PHP, Node.js, v.v.).

**Cách xử lý:**

- Kiểm tra backend service (PHP, Node.js) có đang chạy không:
    
    `systemctl status php-fpmsystemctl status node`
    
- Kiểm tra cấu hình Nginx hoặc Apache để chắc chắn đã trỏ đúng địa chỉ IP hoặc socket.

id: be278398e5d445cca9a7b212b850bb0d
parent_id: bc33dce65848438199af0fd3912185dd
created_time: 2025-04-22T09:47:48.337Z
updated_time: 2025-04-23T07:36:38.444Z
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
user_created_time: 2025-04-22T09:47:48.337Z
user_updated_time: 2025-04-23T07:36:38.444Z
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