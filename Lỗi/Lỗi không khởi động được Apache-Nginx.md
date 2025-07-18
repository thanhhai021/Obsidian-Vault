Lỗi không khởi động được Apache/Nginx

## **Lỗi không khởi động được Apache/Nginx**

**Triệu chứng:**

- `systemctl start apache2` hoặc `nginx` báo lỗi.
    
- Báo "Address already in use" hoặc "port in use".
    

**Nguyên nhân:**

- Port 80/443 đã bị chiếm (thường do service khác: nginx vs apache).

**Cách xử lý:**

`# Kiểm tra port đang dùng:netstat -tulpn | grep :80# Nếu trùng, dừng dịch vụ kia hoặc cấu hình lại port.`

id: 76cda65ecf794fdcb04ee2382a746d81
parent_id: bc33dce65848438199af0fd3912185dd
created_time: 2025-04-22T09:29:50.710Z
updated_time: 2025-04-23T07:36:21.773Z
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
user_created_time: 2025-04-22T09:29:50.710Z
user_updated_time: 2025-04-23T07:36:21.773Z
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