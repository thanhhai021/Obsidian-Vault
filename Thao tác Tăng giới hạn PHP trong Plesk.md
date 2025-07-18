Thao tác Tăng giới hạn PHP trong Plesk

### **Tăng giới hạn PHP trong Plesk**

####  1. **Sửa trực tiếp file `php.ini` theo đường dẫn**

Plesk lưu cấu hình PHP theo phiên bản, bạn sửa tất cả các file tương ứng:

`sudo nano /opt/plesk/php/8.1/etc/php.ini`

Tìm và chỉnh sửa các dòng:

`memory_limit = 256Mupload_max_filesize = 64Mpost_max_size = 64M`

> Lưu lại sau khi chỉnh: `Ctrl + O`, `Enter`, rồi `Ctrl + X`.

* * *

#### 2\. **Áp dụng cho từng chế độ PHP handler**

- **Dedicated FPM application**
    
- **FPM application**
    
- **FastCGI application**
    

Plesk dùng 1 file `php.ini` chung cho mỗi phiên bản, nhưng mỗi handler có thể override bằng file pool hoặc `.user.ini`. Để chắc chắn, bạn nên:

Chỉnh ở file `php.ini` chính  
 Vào Plesk UI để kiểm tra handler nào đang dùng và áp dụng tương ứng

* * *

####  3. **Khởi động lại dịch vụ PHP**

`sudo service plesk-php81-fpm restart`

id: d25fc25844be4a448c4fccd655086523
parent_id: bc33dce65848438199af0fd3912185dd
created_time: 2025-04-15T07:10:31.467Z
updated_time: 2025-04-23T07:32:32.041Z
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
user_created_time: 2025-04-15T07:10:31.467Z
user_updated_time: 2025-04-23T07:32:32.041Z
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