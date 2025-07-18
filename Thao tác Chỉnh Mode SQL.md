Thao tác Chỉnh Mode SQL

Chỉnh Mode SQL

vi /etc/my.cnf  
sql_mode = "NO_ZERO_IN_DATE,NO_ZERO_DATE,ERROR_FOR_DIVISION_BY_ZERO,NO_AUTO_CREATE_USER,NO_ENGINE_SUBSTITUTION"

systemctl restart mysqld  
tắt:  
\\\[mysqld\\\]  
sql_mode=NO_ENGINE_SUBSTITUTION  
\\------------------------------

đổi user đăng nhập admin wordpress nằm trong phpAdmin

name_user của database đó.

đổi pass MD5

id: a1a5e9e40b9c4af89422a047a860c486
parent_id: bc33dce65848438199af0fd3912185dd
created_time: 2025-04-15T07:35:20.174Z
updated_time: 2025-04-15T08:56:31.190Z
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
user_created_time: 2025-04-15T07:35:20.174Z
user_updated_time: 2025-04-15T08:56:31.190Z
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