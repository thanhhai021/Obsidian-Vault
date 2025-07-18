Fix lỗi Fatal Error do thiếu file theme

## **LỖI CHÍNH: Fatal Error do thiếu file theme**

### **Thông báo lỗi**

&nbsp;

`require_once(...functions.php): Failed to open stream: No such file or directory Fatal error: Uncaught Error: Failed opening required ...`

### **Nguyên nhân**

- File `functions.php` trong theme **Flatsome** bị **mất hoặc hỏng** tại đường dẫn:
    
    swift
    
    &nbsp;
    
    `wp-content/themes/flatsome/inc/admin/advanced/functions/functions.php`
    

* * *

## **Cách khắc phục**

### 1\. **Kiểm tra sự tồn tại của file**

- Vào **cPanel > File Manager** hoặc dùng **FTP**.
    
- Kiểm tra thư mục:
    
    swift
    
    &nbsp;
    
    `wp-content/themes/flatsome/inc/admin/advanced/functions/`
    
- Nếu file `functions.php` **không có**, chuyển sang bước 2.
    

* * *

### 2\. **Tải lại theme gốc từ Flatsome**

- Tải lại theme từ trang chính thức của **Flatsome**.
    
- Chỉ **ghi đè thư mục theme** hoặc **upload lại toàn bộ thư mục `flatsome`** nếu cần.
    
- **Không xóa theme cũ** nếu bạn chưa backup, để tránh mất tuỳ chỉnh.
    

* * *

### 3\. **Khôi phục từ bản sao lưu**

- Nếu bạn có **backup**, hãy **phục hồi lại toàn bộ thư mục theme**.

* * *

### 4\. **Kiểm tra quyền file**

- Quyền đúng là:
    
    - **Thư mục**: `755`
        
    - **File**: `644`
        

* * *

### 5\. **Bật debug trong WordPress để xem lỗi rõ hơn**

**Mở file `wp-config.php`**, thêm dòng sau nếu chưa có:

php

`define( 'WP_DEBUG', true );define( 'WP_DEBUG_LOG', true );define( 'WP_DEBUG_DISPLAY', false );`

→ File log lỗi sẽ được ghi ở: `/wp-content/debug.log`

* * *

### 6\. **Lỗi ở `meta.php` (nếu có)**

- Nếu xuất hiện lỗi liên quan `meta.php` trong thư mục `wp-includes/`, có thể:
    
    - File bị lỗi, thiếu dòng code hoặc bị chỉnh sửa sai.
- Cách xử lý:
    
    - Tải **source WordPress gốc** đúng phiên bản bạn đang dùng từ wordpress.org.
        
    - Giải nén và **lấy lại file `wp-includes/meta.php`**, chép đè lên file trên host.

id: 4380fa0bba32428893632c35ab452249
parent_id: bc33dce65848438199af0fd3912185dd
created_time: 2025-04-15T08:01:27.223Z
updated_time: 2025-04-23T07:19:56.223Z
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
user_created_time: 2025-04-15T08:01:27.223Z
user_updated_time: 2025-04-23T07:19:56.223Z
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