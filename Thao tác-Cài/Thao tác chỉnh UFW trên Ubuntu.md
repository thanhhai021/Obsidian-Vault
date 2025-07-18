Thao tác chỉnh UFW trên Ubuntu

UFW trên Ubuntu

UFW trên Ubuntu:

sudo ufw allow 8888/tcp  
sudo ufw reload  
Nếu bạn sử dụng firewalld trên CentOS:

sudo firewall-cmd --zone=public --add-port=8888/tcp --permanent  
sudo firewall-cmd --reload  
Nếu bạn đang sử dụng CSF: Mở tệp cấu hình csf.conf và thêm cổng 8888 vào danh sách các cổng được phép:

id: 7f74b0f76ae84b52a84ba2bb663b3ce3
parent_id: bc33dce65848438199af0fd3912185dd
created_time: 2025-04-15T07:53:41.650Z
updated_time: 2025-04-15T09:06:45.668Z
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
user_created_time: 2025-04-15T07:53:41.650Z
user_updated_time: 2025-04-15T09:06:45.668Z
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