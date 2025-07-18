Phân vùng mới trên Linux

# Hướng dẫn tạo, format và mount phân vùng mới trên Linux

## 1\. Kiểm tra phân vùng hiện tại

bash

CopyEdit

`lsblk`

hoặc

bash

CopyEdit

`fdisk -l /dev/sda`

Xác định phân vùng đã có, phần còn dư chưa phân vùng.

* * *

## 2\. Tạo phân vùng mới bằng gdisk (ổ GPT)

bash

CopyEdit

`gdisk /dev/sda`

- Nhấn `n` để tạo phân vùng mới
    
- Nhấn Enter cho partition number, first sector, last sector (mặc định dùng toàn bộ dung lượng còn lại)
    
- Mã phân vùng: `8300` (Linux filesystem)
    
- Nhấn `w` để ghi thay đổi
    
- Xác nhận `y`
    

* * *

## 3\. Để kernel nhận bảng phân vùng mới

bash

CopyEdit

`partprobe /dev/sda`

hoặc

bash

CopyEdit

`kpartx -a /dev/sda`

Nếu không thấy phân vùng mới `/dev/sdaX`, hãy reboot hệ thống:

bash

CopyEdit

`reboot`

* * *

## 4\. Format phân vùng mới thành ext4

Giả sử phân vùng mới là `/dev/sda4`, format:

bash

CopyEdit

`mkfs.ext4 /dev/sda4`

Sau khi format, phân vùng sẽ có `UUID` mới.

* * *

## 5\. Lấy UUID phân vùng mới

bash

CopyEdit

`blkid /dev/sda4`

Output ví dụ:

pgsql

CopyEdit

`/dev/sda4: UUID="abcd1234-5678-90ef-ghij-klmnopqrstuv" TYPE="ext4"`

* * *

## 6\. Tạo thư mục mount và mount phân vùng mới

bash

CopyEdit

`mkdir /mnt/storagemount /dev/sda4 /mnt/storage`

Kiểm tra:

bash

CopyEdit

`df -h | grep /mnt/storage`

* * *

## 7\. Cấu hình tự động mount qua `/etc/fstab`

Sửa file `/etc/fstab`:

bash

CopyEdit

`nano /etc/fstab`

Thêm dòng sau (thay UUID bằng giá trị từ bước 5):

ini

CopyEdit

`UUID=abcd1234-5678-90ef-ghij-klmnopqrstuv /mnt/storage ext4 defaults 0 2`

* * *

## 8\. Reload cấu hình và mount tất cả phân vùng trong fstab

bash

CopyEdit

`systemctl daemon-reexecmount -a`

Kiểm tra lại:

bash

CopyEdit

`df -h | grep /mnt/storage`

* * *

## 9\. Kiểm tra tự động mount sau khi reboot

bash

CopyEdit

`reboot`

Sau khi khởi động lại:

bash

CopyEdit

`df -h | grep /mnt/storage`

id: a272f4a5bf8c42248552be5542e0a05f
parent_id: bc33dce65848438199af0fd3912185dd
created_time: 2025-06-04T01:42:19.409Z
updated_time: 2025-06-16T06:01:49.542Z
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
user_created_time: 2025-06-04T01:42:19.409Z
user_updated_time: 2025-06-16T06:01:49.542Z
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