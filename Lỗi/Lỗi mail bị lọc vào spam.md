Lỗi mail bị lọc vào spam (tiếp tục vấn đề SPF/DKIM)

## **Lỗi mail bị lọc vào spam (tiếp tục vấn đề SPF/DKIM)**

**Nguyên nhân:**

- Thiếu cấu hình SPF/DKIM hoặc cấu hình sai.
    
- Không có DMARC hoặc cấu hình không đúng.
    
- Dấu hiệu spam trong nội dung mail (từ khóa, quá nhiều hình ảnh, v.v.).
    

**Cách xử lý:**

- **SPF**: Đảm bảo bạn có bản ghi SPF đúng:
    
    `v=spf1 mx a ip4:YOUR.SERVER.IP ~all`
    
- **DKIM**: Cài OpenDKIM và thêm bản ghi TXT vào DNS.
    
- **DMARC**: Cấu hình DMARC record:
    
    &nbsp;
    
    `v=DMARC1; p=none; rua=mailto:you@example.com`

id: 20a9e03e4b5a42fca03378b43cd01237
parent_id: bc33dce65848438199af0fd3912185dd
created_time: 2025-04-22T09:41:05.480Z
updated_time: 2025-04-23T07:36:11.275Z
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
user_created_time: 2025-04-22T09:41:05.480Z
user_updated_time: 2025-04-23T07:36:11.275Z
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