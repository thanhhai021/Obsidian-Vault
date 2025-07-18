Build lại PHP tùy chỉnh trên DirectAdmin

### **Build lại PHP tùy chỉnh trên DirectAdmin**

#### 1\. **Kiểm tra phiên bản hiện tại**

`vi /usr/local/directadmin/custombuild/options.conf`

> Kiểm tra phiên bản PHP hiện tại trong file `options.conf` hoặc `version.txt`.

* * *

#### 2\. **Thay đổi phiên bản PHP muốn cài**

`cd /usr/local/directadmin/custombuildnano options.conf`

> Tìm dòng có tên `php1_release`, `php2_release`,... và sửa thành phiên bản PHP mong muốn (ví dụ `8.1` hoặc `8.2`).

* * *

#### 3\. **Cập nhật và build lại**

`./build update./build php n./build rewrite_confs`

id: cc81de771fdf4840b650914d87ad4cfa
parent_id: bc33dce65848438199af0fd3912185dd
created_time: 2025-04-15T07:09:00.173Z
updated_time: 2025-04-15T08:46:59.660Z
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
user_created_time: 2025-04-15T07:09:00.173Z
user_updated_time: 2025-04-15T08:46:59.660Z
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