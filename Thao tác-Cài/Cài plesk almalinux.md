Cài plesk almalinux

## 1\. **Plesk trên AlmaLinux (chuẩn)**

Plesk hỗ trợ **AlmaLinux 8 và 9** chính thức. Cách cài:

### Bước 1: Cập nhật hệ thống

`dnf update -y`

###  Bước 2: Cài Plesk (bản mới nhất)

`curl -O https://autoinstall.plesk.com/plesk-installerchmod +x plesk-installer./plesk-installer`

Hoặc dùng cài đặt im lặng:

`sh plesk-installer --select-release-latest --install-component panel`

Xong, truy cập:  
`https://your-server-ip:8443`

id: f940123c08e94c32b6587ab1c59e5773
parent_id: bc33dce65848438199af0fd3912185dd
created_time: 2025-04-15T06:58:12.961Z
updated_time: 2025-04-23T07:17:16.871Z
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
user_created_time: 2025-04-15T06:58:12.961Z
user_updated_time: 2025-04-23T07:17:16.871Z
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