Website load chậm / timeout

## **Website load chậm / timeout**

**Nguyên nhân:**

- Server yếu / thiếu RAM / CPU.
    
- Lỗi vòng lặp redirect.
    
- PHP-FPM, MySQL hoặc dịch vụ nền bị treo.
    

**Cách khắc phục:**

- Kiểm tra tài nguyên bằng `top`, `htop`, `free -m`.
    
- Kiểm tra lỗi redirect bằng Devtools > Network.
    
- Restart PHP-FPM: `systemctl restart php-fpm`
    
- Kiểm tra `slow query` trong MySQL.

id: a0208b1694aa4c31bbc19d2723e5f086
parent_id: bc33dce65848438199af0fd3912185dd
created_time: 2025-04-22T09:24:15.629Z
updated_time: 2025-04-23T07:34:25.444Z
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
user_created_time: 2025-04-22T09:24:15.629Z
user_updated_time: 2025-04-23T07:34:25.444Z
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