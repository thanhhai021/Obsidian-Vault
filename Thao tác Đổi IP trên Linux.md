Thao tác Đổi IP trên Linux

Đổi IP Almalinux

Xem các interface

nmcli con show\\

Đổi IP

nmcli con mod ens33 ipv4.addresses 192.168.0.18/24

nmcli con mod ens33 ipv4.gateway 192.168.0.1

nmcli con mod ens33 ipv4.dns "8.8.8.8 1.1.1.1"

nmcli con mod ens33 ipv4.method manual

nmcli con up ens160

id: de9d43f77b1c4f05a99b16ecaf712765
parent_id: bc33dce65848438199af0fd3912185dd
created_time: 2025-04-15T07:39:28.156Z
updated_time: 2025-04-18T07:29:40.583Z
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
user_created_time: 2025-04-15T07:39:28.156Z
user_updated_time: 2025-04-18T07:29:40.583Z
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