Fix lỗi 404

Nguyên nhân sai đường dẫn truy cập source web do kh di chuyển coppy source web

Cách khắc phục:  
Tạo chuyển hường bằng cách sửa file htacess và index.php

Mở file /public_html/index.php, tìm dòng:

require( dirname( _*FILE*_ ) . '/wp-blog-header.php' );  
 sửa thành:  
require( dirname( _*FILE*_ ) . '/dvdl/wp-blog-header.php' );

id: d178b6f6a86a4b6d9321fe06f4018a60
parent_id: bc33dce65848438199af0fd3912185dd
created_time: 2025-04-15T08:42:29.733Z
updated_time: 2025-04-23T07:19:38.091Z
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
user_created_time: 2025-04-15T08:42:29.733Z
user_updated_time: 2025-04-23T07:19:38.091Z
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