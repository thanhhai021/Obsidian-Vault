Dịch vụ Docker không chạy (Docker container bị crash)

## **Dịch vụ Docker không chạy (Docker container bị crash)**

**Nguyên nhân:**

- Container bị crash do lỗi cấu hình hoặc tài nguyên hệ thống thiếu.
    
- Không đủ quyền truy cập đối với container.
    

**Cách xử lý:**

- Kiểm tra trạng thái container:
    
    &nbsp;
    
    `docker ps -a`
    
- Xem log của container:
    
    &nbsp;
    
    `docker logs <container_id>`
    
- Nếu container bị crash vì thiếu tài nguyên, tăng giới hạn tài nguyên trong file cấu hình `docker-compose.yml`:
    
    yaml
    
    `resources: limits: memory: 500M cpus: '0.5'`

id: f6859a8ef2c44006b18b19e9440f85ab
parent_id: bc33dce65848438199af0fd3912185dd
created_time: 2025-04-22T09:45:30.318Z
updated_time: 2025-04-23T07:18:47.980Z
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
user_created_time: 2025-04-22T09:45:30.318Z
user_updated_time: 2025-04-23T07:18:47.980Z
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