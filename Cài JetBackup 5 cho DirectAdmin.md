Cài JetBackup 5 cho DirectAdmin

## Cài đặt JetBackup 5 cho DirectAdmin

### Trước khi chạy lệnh cài:

**Chỉnh sửa lại file repo "Base-Centos"** (có thể là `/etc/yum.repos.d/CentOS-Base.repo`) để bật/tắt repo cần thiết.

### Lệnh cài đặt:

`yum install jetbackup5-directadmin -y \--disablerepo=* \--enablerepo=base,cloudlinux-base,cloudlinux-x86_64-server-7,jetapps,jetapps-stable`

* * *

## Kiểm tra ổ đĩa sau khi cài OS

Chạy lệnh:

`lsblk -f`

id: d86ee80d32c14b1fa6ac54cca9b3e7ac
parent_id: bc33dce65848438199af0fd3912185dd
created_time: 2025-04-15T07:55:53.781Z
updated_time: 2025-04-23T07:15:33.766Z
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
user_created_time: 2025-04-15T07:55:53.781Z
user_updated_time: 2025-04-23T07:15:33.766Z
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