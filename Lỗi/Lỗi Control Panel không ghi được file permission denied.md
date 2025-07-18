Control Panel không ghi được file (permission denied)**

## **Control Panel không ghi được file (permission denied)**

**Nguyên nhân:**

- File/folder sai chủ sở hữu (`owner`).
    
- Dịch vụ web (Apache, Nginx) không có quyền ghi.
    

**Cách khắc phục:**

- Sửa owner:
    
    &nbsp;
    
    `chown -R user:user /home/user/public_html`
    
- Chmod thư mục đúng cách:
    
    &nbsp;
    
    `find /home/user/public_html -type d -exec chmod 755 {} \;find /home/user/public_html -type f -exec chmod 644 {} \;`

id: 25c508e4f95149738be07374f829a007
parent_id: bc33dce65848438199af0fd3912185dd
created_time: 2025-04-22T09:27:16.235Z
updated_time: 2025-04-22T09:27:45.170Z
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
user_created_time: 2025-04-22T09:27:16.235Z
user_updated_time: 2025-04-22T09:27:45.170Z
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