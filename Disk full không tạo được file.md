Disk full / không tạo được file

## **Disk full / không tạo được file**

**Nguyên nhân:**

- Ổ đĩa đầy.
    
- File log quá lớn.
    

**Cách khắc phục:**

- Kiểm tra dung lượng: `df -h`
    
- Tìm file nặng:
    
    &nbsp;
    
    `du -ah /var | sort -rh | head -20`
    
- Dọn log:
    
    &nbsp;
    
    `truncate -s 0 /var/log/httpd/access_logtruncate -s 0 /var/log/httpd/error_log`

id: ab78c9eb7d1e485a98d6aff033a5f764
parent_id: bc33dce65848438199af0fd3912185dd
created_time: 2025-04-22T09:27:46.668Z
updated_time: 2025-04-23T07:18:58.348Z
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
user_created_time: 2025-04-22T09:27:46.668Z
user_updated_time: 2025-04-23T07:18:58.348Z
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