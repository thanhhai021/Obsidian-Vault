Thao tác Cấu hình ssh để remote Alma

Mở file cấu hình SSH:

nano /etc/ssh/sshd_config

Đảm bảo có dòng sau

PermitRootLogin yes

PasswordAuthentication yes

Nếu PermitRootLogin đang là no hoặc prohibit-password, bạn cần sửa lại.

Lưu file và khởi động lại dịch vụ:

systemctl restart sshd

id: c93aaa37d7b34c739c514863ffd2d96e
parent_id: bc33dce65848438199af0fd3912185dd
created_time: 2025-04-15T06:47:39.826Z
updated_time: 2025-04-15T08:57:32.398Z
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
user_created_time: 2025-04-15T06:47:39.826Z
user_updated_time: 2025-04-15T08:57:32.398Z
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