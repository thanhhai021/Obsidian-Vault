Web không load CSS/JS (giao diện vỡ) sau khi bật HTTPS

## **Web không load CSS/JS (giao diện vỡ) sau khi bật HTTPS**

**Nguyên nhân:**

- Trình duyệt chặn nội dung “mixed content”.
    
- Website vẫn gọi tài nguyên qua `http://` thay vì `https://`.
    

**Cách xử lý:**

- Sửa trong database (nếu WordPress): đổi tất cả `http://` thành `https://`.
    
    &nbsp;
    
    `wp search-replace 'http://yourdomain.com' 'https://yourdomain.com'`
    
- Bật `Content-Security-Policy` đúng nếu dùng CDN.

id: d81ce12b83c64f108c75c079c8bb8bd3
parent_id: bc33dce65848438199af0fd3912185dd
created_time: 2025-04-22T09:34:20.181Z
updated_time: 2025-04-23T07:34:37.130Z
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
user_created_time: 2025-04-22T09:34:20.181Z
user_updated_time: 2025-04-23T07:34:37.130Z
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