Hướng dẫn cấu hình Proxmox VE kết nối Proxmox Backup Server (PBS) với SSL và API

# Hướng dẫn cấu hình Proxmox VE kết nối Proxmox Backup Server (PBS) với SSL và API Token

## 1\. Tạo CSR và self-signed certificate trên PBS

1.  Tạo private key (nếu chưa có):

bash

CopyEdit

`openssl genrsa -out /etc/proxmox-backup/ssl/proxmox-backup.key 2048`

2.  Tạo CSR (Certificate Signing Request):

bash

CopyEdit

`openssl req -new -key /etc/proxmox-backup/ssl/proxmox-backup.key -out /etc/proxmox-backup/ssl/request.csr`

- Khi nhập các thông tin, chú ý phần **Common Name (CN)** điền IP hoặc hostname của PBS.

3.  Tạo self-signed certificate từ CSR:

bash

CopyEdit

`openssl x509 -req -days 365 -in /etc/proxmox-backup/ssl/request.csr -signkey /etc/proxmox-backup/ssl/proxmox-backup.key -out /etc/proxmox-backup/ssl/proxmox-backup.pem`

## 2\. Upload certificate và key vào giao diện PBS

- Vào giao diện web PBS, upload file `/etc/proxmox-backup/ssl/proxmox-backup.pem` và `/etc/proxmox-backup/ssl/proxmox-backup.key` để PBS dùng certificate này.

## 3\. Tạo User và API Token trên PBS

1.  Tạo user API riêng biệt (ví dụ: `pve-backup`):

bash

CopyEdit

`pveum user add pve-backup@pbs --comment "User for PVE backup"`

2.  Tạo API Token cho user:

bash

CopyEdit

`pveum token add pve-backup@pbs PVEBackupToken`

3.  Cấp quyền đầy đủ trên PBS cho user/token

- Vào giao diện PBS → Permissions → Add
    
- Gán quyền `Admin` hoặc ít nhất `Datastore.Audit` + `Datastore.Allocate` cho user `pve-backup@pbs` trên datastore bạn muốn backup (ví dụ `backup-raid5`).
    

## 4\. Cấu hình Storage Backup trên Proxmox VE

1.  Thêm Storage Backup:

- ID: tên tự đặt, ví dụ `pbs-storage`
    
- Type: Proxmox Backup Server
    
- Server: IP hoặc hostname PBS
    
- Datastore: tên datastore trên PBS, ví dụ `backup-raid5`
    
- API Token ID: `pve-backup@pbs!PVEBackupToken`
    
- API Token Secret: token bí mật lấy từ bước tạo token
    
- Certificate: upload hoặc chỉ định certificate `.pem` đã tạo
    

2.  Lưu cấu hình.

## 5\. Kiểm tra và xử lý lỗi

- Nếu gặp lỗi `401 Unauthorized` hoặc `Cannot find datastore`, kiểm tra lại:
    
    - API Token đúng và được cấp quyền trên datastore.
        
    - Tên datastore chính xác tồn tại trên PBS.
        
    - User/token có đủ quyền (Admin hoặc quyền cụ thể).
        
- Kiểm tra lại file certificate đã upload đúng trên PBS và PVE.
    

* * *

Nếu bạn làm đúng các bước trên thì Proxmox VE sẽ kết nối được với PBS, sử dụng SSL và API Token để backup an toàn và hiệu quả.

Bạn muốn mình hỗ trợ thêm phần nào chi tiết hơn không?

id: a54921033dfb487c8fd53f42f922e375
parent_id: bc33dce65848438199af0fd3912185dd
created_time: 2025-06-04T02:55:07.821Z
updated_time: 2025-06-04T02:55:19.091Z
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
user_created_time: 2025-06-04T02:55:07.821Z
user_updated_time: 2025-06-04T02:55:19.091Z
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