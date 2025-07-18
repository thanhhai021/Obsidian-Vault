LỖI VỀ MAIL SERVER & BẢO MẬT HỆ THỐNG

## LỖI VỀ MAIL SERVER & BẢO MẬT HỆ THỐNG

* * *

## Lỗi "421 Too many connections" khi gửi mail

**Nguyên nhân:**

- Mail server của bạn bị flood bởi các kết nối đồng thời quá nhiều từ một hoặc nhiều IP.
    
- Thường gặp khi có botnet hoặc người gửi mail không hợp lệ.
    

**Cách xử lý:**

- Thêm giới hạn số kết nối tối đa trong Postfix:
    
    `smtpd_client_connection_count_limit = 10smtpd_client_connection_rate_limit = 20`
    
- Kiểm tra log và IP:
    
    `tail -f /var/log/maillog`

id: c3272d43b9134607b210e29123d918fa
parent_id: bc33dce65848438199af0fd3912185dd
created_time: 2025-04-22T09:40:11.630Z
updated_time: 2025-04-23T07:26:38.521Z
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
user_created_time: 2025-04-22T09:40:11.630Z
user_updated_time: 2025-04-23T07:26:38.521Z
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