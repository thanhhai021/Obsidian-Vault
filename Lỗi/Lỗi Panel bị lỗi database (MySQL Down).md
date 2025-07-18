Panel bị lỗi database (MySQL Down)

## **Panel bị lỗi database (MySQL Down)**

**Nguyên nhân:**

- MySQL bị crash do hết RAM, disk, file bị lỗi.

**Cách khắc phục:**

- Kiểm tra trạng thái: `systemctl status mysqld`
    
- Restart: `systemctl restart mysqld`
    
- Kiểm tra dung lượng: `df -h`, `du -sh /var/lib/mysql`
    
- Dò lỗi log: `/var/log/mysqld.log` hoặc `/var/log/mysql/error.log`

id: 1aef91ccaf444ddfa053e532cbeb9472
parent_id: bc33dce65848438199af0fd3912185dd
created_time: 2025-04-22T09:25:21.719Z
updated_time: 2025-04-22T09:25:40.574Z
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
user_created_time: 2025-04-22T09:25:21.719Z
user_updated_time: 2025-04-22T09:25:40.574Z
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