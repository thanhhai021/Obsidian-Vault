Thao tác Cấu hình chuyển hướng web

\-Apache- htacess

RewriteEngine On  
RewriteCond %{HTTP_HOST} ^old-domain\\.com$ \[NC\]  
RewriteRule ^(.\*)$ http://new-domain.com/$1 \[L,R=301\]

Nginx 

server {  
    listen 80;  
    server_name old-domain.com;  
    return 301 http://new-domain.com$request_uri;  
}

\-Bằng panel

Chọn mục Redirect cấu hình chuyển hướng

\-Cấu hình DNS nếu có hỗ trợ bản ghi này

id: 8bdd2bb1da9d48429d3a41b01001fa39
parent_id: bc33dce65848438199af0fd3912185dd
created_time: 2025-04-21T02:16:51.818Z
updated_time: 2025-04-21T02:24:38.026Z
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
user_created_time: 2025-04-21T02:16:51.818Z
user_updated_time: 2025-04-21T02:24:38.026Z
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