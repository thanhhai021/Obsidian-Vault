Service không tự khởi động sau khi reboot

## **Service không tự khởi động sau khi reboot**

**Nguyên nhân:**

- Dịch vụ chưa được cấu hình để tự khởi động cùng hệ thống.
    
- Dịch vụ có dependency nhưng không khởi động đúng thứ tự.
    

**Cách xử lý:**

- Đảm bảo dịch vụ được bật tự động khởi động:
    
    &nbsp;
    
    `systemctl enable your-service-name`
    
- Kiểm tra trạng thái dịch vụ:
    
    &nbsp;
    
    `systemctl is-enabled your-service-name`

id: feb986ab4c2f472daa0ae73442805e52
parent_id: bc33dce65848438199af0fd3912185dd
created_time: 2025-04-22T09:46:08.792Z
updated_time: 2025-04-22T09:46:22.432Z
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
user_created_time: 2025-04-22T09:46:08.792Z
user_updated_time: 2025-04-22T09:46:22.432Z
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