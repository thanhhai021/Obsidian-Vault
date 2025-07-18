Thao tác Xóa định dạng & Định dạng lại Disk Ceph

### **Xóa định dạng & Định dạng lại Disk Ceph**

#### 1\. **Xem danh sách thiết bị Ceph đang sử dụng**

&nbsp;

`dmsetup ls`

Ví dụ đầu ra:

`ceph--ffd9fd78--94fa--4776--9737--7ac2d9421420-osd--block--7832eec2--d1cc--4d70--b84b--64aa728de909 (252:1)`

#### 2\. **Xóa thiết bị Ceph khỏi mapper**

`dmsetup remove /dev/mapper/ceph--<...> # Dán đúng tên thiết bị ở bước trên`

#### 3\. **Tạo bảng phân vùng GPT mới (xóa toàn bộ dữ liệu cũ)**

&nbsp;

`parted -s /dev/sdb mklabel gpt`

> 💡 *Lưu ý*: `/dev/sdb` là ổ đĩa bạn muốn định dạng lại, kiểm tra kỹ để tránh xóa nhầm.

id: 5cbedb1a55804674a4270eb9ccd70321
parent_id: bc33dce65848438199af0fd3912185dd
created_time: 2025-04-15T07:59:09.731Z
updated_time: 2025-04-15T09:07:17.917Z
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
user_created_time: 2025-04-15T07:59:09.731Z
user_updated_time: 2025-04-15T09:07:17.917Z
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