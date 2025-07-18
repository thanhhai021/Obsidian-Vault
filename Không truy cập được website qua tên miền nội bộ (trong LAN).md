Không truy cập được website qua tên miền nội bộ (trong LAN)

## **Không truy cập được website qua tên miền nội bộ (trong LAN)**

**Nguyên nhân:**

- DNS nội bộ chưa đúng.
    
- Tường lửa chặn từ IP cục bộ.
    

**Cách xử lý:**

- Thêm tên miền vào file `hosts`:
    
    &nbsp;
    
    `echo "192.168.1.10 tenmien.local" >> /etc/hosts`
    
- Kiểm tra port mở trong LAN: `nmap 192.168.1.10`

id: eb690d613111415b882490fdc4b1d9fc
parent_id: bc33dce65848438199af0fd3912185dd
created_time: 2025-04-22T09:32:09.394Z
updated_time: 2025-04-23T07:21:52.016Z
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
user_created_time: 2025-04-22T09:32:09.394Z
user_updated_time: 2025-04-23T07:21:52.016Z
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