Cài đặt Proxmox Backup Server (PBS)

## 1\. Cài đặt Proxmox Backup Server (PBS)

- Cài PBS trên máy, thường cài trên ổ riêng (không bắt buộc RAID 5 cho OS).
    
- Đảm bảo OS và PBS chạy ổn định.
    

* * *

## 2\. Tạo RAID 5 với 3 ổ dữ liệu bằng `mdadm`

`apt update`

`apt install mdadm`

`mdadm --create --verbose /dev/md0 --level=5 --raid-devices=3 /dev/sdb /dev/sdc /dev/sdd ` 

`mkfs.ext4 /dev/md0`

`mkdir /raid5`

`mount /dev/md0 `  `/raid5`

`blkid /dev/md0`    <span style="color: rgb(0, 0, 0);">\# Lấy UUID</span>

- Thêm UUID vào `/etc/fstab` để tự động mount khi reboot:

`UUID=xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx /raid5 ext4 defaults 0 2`

`UUID=99e71ac5-aa41-46b6-8324-f6b5d6e996d8 /raid5 ext4 defaults 0 2`

`vd : UUID=b5fcd561-296e-45d9-86f7-cfe00ebb07ad /PromoxBackupServer ext4 defaults 0 2`

- Lưu cấu hình RAID để nhận dạng lại sau reboot:

`mdadm --detail --scan >> /etc/mdadm/mdadm.conf`

&nbsp;

apt update

apt install mdadm

mdadm --create --verbose /dev/md0 --level=5 --raid-devices=3 /dev/sdb /dev/sdc /dev/sdd  
mkfs.ext4 /dev/md0

mkdir /raid5

mount /dev/md0 /raid5

blkid /dev/md0 #  
<br/><br/>

* * *

## 3\. Cấu hình Proxmox Backup Server dùng RAID 5 làm datastore

- Vào Web GUI PBS: `https://<IP-PBS>:8007` đăng nhập `root@pam`
    
- **Datastore → Add**
    
- Name: `backup-raid5`
    
- Path: `/raid5`
    
- Tạo và phân quyền nếu cần.
    

* * *

## 4\. Backup thủ công từ Proxmox VE sang PBS

- Qua GUI Proxmox VE: VM → Backup → Backup now → chọn Storage là datastore PBS.
    
- Hoặc CLI:
    

`vzdump <VMID> --storage backup-raid5 --mode snapshot`

* * *

## 5\. Restore thủ công từ PBS về Proxmox VE

- Qua GUI Proxmox VE: Backup → chọn bản backup → Restore.
    
- Hoặc CLI:
    

`qmrestore /path/to/backup/file.vma.zst <VMID>`

* * *

## 6\. Backup/Restore thủ công trực tiếp trên PBS (dữ liệu file/folder)

- Backup:

`proxmox-backup-client backup --repository root@pbs:backup-raid5/mybackup /path/to/data`

- Restore:

`proxmox-backup-client restore --repository root@pbs:backup-raid5/mybackup /path/to/restore`

id: c310f9b046e54a46aa15481a19a3010f
parent_id: bc33dce65848438199af0fd3912185dd
created_time: 2025-05-26T01:42:05.548Z
updated_time: 2025-06-09T09:24:34.669Z
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
user_created_time: 2025-05-26T01:42:05.548Z
user_updated_time: 2025-06-09T09:24:34.669Z
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