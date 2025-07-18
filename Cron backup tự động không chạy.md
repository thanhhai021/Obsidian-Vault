Cron backup tự động không chạy**

## **Cron backup tự động không chạy**

**Nguyên nhân:**

- Script thiếu quyền.
    
- Đường dẫn tuyệt đối không đúng trong môi trường cron.
    

**Cách xử lý:**

`# Trong script nên dùng đường dẫn đầy đủ:/usr/bin/mysqldump -u root ...# Và thêm log:* * * * * /root/backup.sh >> /var/log/cron-backup.log 2>&1`

id: 9f4e27ab336a423097b7cb711dd8b9d1
parent_id: bc33dce65848438199af0fd3912185dd
created_time: 2025-04-22T09:35:04.935Z
updated_time: 2025-04-23T07:18:22.238Z
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
user_created_time: 2025-04-22T09:35:04.935Z
user_updated_time: 2025-04-23T07:18:22.238Z
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