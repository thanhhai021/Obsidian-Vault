Lỗi chuyển hướng cpanel htacess

\# Kích hoạt mod_rewrite  
RewriteEngine On

\# Chuyển hướng HTTP sang HTTPS (nếu cần)  
RewriteCond %{HTTPS} off  
RewriteRule ^ https://%{HTTP_HOST}%{REQUEST_URI} \[L,R=301\]

\# Kiểm tra nếu domain là example.com (có phân biệt chữ hoa chữ thường)  
RewriteCond %{HTTP_HOST} ^example\\.com$ \[NC\]

\# Wildcard Redirect: Chuyển hướng tất cả các URL từ example.com sang newdomain.com  
RewriteRule ^(.\*)$ http://newdomain.com/$1 \[L,R=301\]

id: 530224bb80d541699109ffd352eb396c
parent_id: bc33dce65848438199af0fd3912185dd
created_time: 2025-04-22T03:41:02.151Z
updated_time: 2025-06-16T06:02:31.792Z
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
user_created_time: 2025-04-22T03:41:02.151Z
user_updated_time: 2025-06-16T06:02:31.792Z
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