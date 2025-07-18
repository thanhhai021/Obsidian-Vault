MySQL bị crash hoặc không khởi động được

## **MySQL bị crash hoặc không khởi động được**

**Nguyên nhân:**

- Lỗi cấu hình trong `my.cnf`.
    
- Thiếu bộ nhớ RAM hoặc đĩa đầy.
    
- Bảng dữ liệu bị lỗi.
    

**Cách xử lý:**

- Kiểm tra log MySQL:
    
    &nbsp;
    
    `tail -f /var/log/mysql/error.log`
    
- Kiểm tra dung lượng đĩa:
    
    `df -h`
    
- Kiểm tra bộ nhớ RAM:
    
    `free -h`
    
- Nếu MySQL crash do bảng dữ liệu, sử dụng `mysqlcheck` để sửa chữa:
    
    &nbsp;
    
    `mysqlcheck -u root -p --auto-repair --all-databases`
    
- Kiểm tra cấu hình MySQL:
    
    `mysqladmin variables`

id: 232e370c68cd475a8c2aa283e24cc87c
parent_id: bc33dce65848438199af0fd3912185dd
created_time: 2025-04-22T09:45:17.670Z
updated_time: 2025-04-23T07:35:39.600Z
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
user_created_time: 2025-04-22T09:45:17.670Z
user_updated_time: 2025-04-23T07:35:39.600Z
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