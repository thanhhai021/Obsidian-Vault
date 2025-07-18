Cài xong Panel như CyberPanel mà không login được

## **Cài xong Panel như CyberPanel mà không login được**

**Nguyên nhân:**

- OpenLiteSpeed chưa chạy hoặc chưa mở port 7080.
    
- CSF chặn port.
    
- SELinux chặn truy cập nội bộ.
    

**Cách xử lý:**

`systemctl restart lscpdcsf -a YOUR.IP.ADDRESSsemanage port -a -t http_port_t -p tcp 7080`

id: 95b47d9cd8d64bc79ae559620f92b7df
parent_id: bc33dce65848438199af0fd3912185dd
created_time: 2025-04-22T09:35:28.079Z
updated_time: 2025-04-23T07:18:04.787Z
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
user_created_time: 2025-04-22T09:35:28.079Z
user_updated_time: 2025-04-23T07:18:04.787Z
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