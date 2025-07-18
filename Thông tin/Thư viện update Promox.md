Thư viện update Promox

## 1\. **Proxmox VE (PVE)**

### Thêm repo **không license (no-subscription)**

- Tạo file `/etc/apt/sources.list.d/pve-no-subscription.list` với nội dung:

nginx

CopyEdit

`deb http://download.proxmox.com/debian/pve bookworm pve-no-subscription`

- Nếu bạn có license, thay bằng repo enterprise trong file `/etc/apt/sources.list.d/pve-enterprise.list`:

nginx

CopyEdit

`deb https://enterprise.proxmox.com/debian/pve bookworm pve-enterprise`

* * *

## 2\. **Proxmox Backup Server (PBS)**

### Thêm repo **không license (no-subscription)**

- Tạo file `/etc/apt/sources.list.d/proxmox-backup.list` với nội dung:

nginx

CopyEdit

`deb http://download.proxmox.com/debian/pbs bookworm pbs-no-subscription`

- Nếu bạn có license, thay bằng repo enterprise:

nginx

CopyEdit

`deb https://enterprise.proxmox.com/debian/pbs bookworm pbs-enterprise`

* * *

## 3\. **Update & Upgrade**

Sau khi thêm repo, chạy lệnh:

bash

CopyEdit

`apt updateapt upgrade -y`

id: d66e2951e6774e5a889cc9d989e05ed8
parent_id: bc33dce65848438199af0fd3912185dd
created_time: 2025-06-03T08:37:51.153Z
updated_time: 2025-06-03T08:38:03.449Z
is_conflict: 0
latitude: 10.82309890
longitude: 106.62966380
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
user_created_time: 2025-06-03T08:37:51.153Z
user_updated_time: 2025-06-03T08:38:03.449Z
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