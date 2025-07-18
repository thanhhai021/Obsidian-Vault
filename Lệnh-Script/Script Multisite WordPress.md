Script Multisite WordPress

Multisite WordPress 3.5 and up If you activated Multisite on WordPress 3.5 or later, use one of these.  WordPress >=3.5 Subfolder Example

# BEGIN WordPress Multisite
# Using subfolder network type: https://wordpress.org/documentation/article/htaccess/#multisite

RewriteEngine On
RewriteRule .* - [E=HTTP_AUTHORIZATION:%{HTTP:Authorization}]
RewriteBase /
RewriteRule ^index\.php$ - [L]

# add a trailing slash to /wp-admin
RewriteRule ^([_0-9a-zA-Z-]+/)?wp-admin$ $1wp-admin/ [R=301,L]

RewriteCond %{REQUEST_FILENAME} -f [OR]
RewriteCond %{REQUEST_FILENAME} -d
RewriteRule ^ - [L]
RewriteRule ^([_0-9a-zA-Z-]+/)?(wp-(content|admin|includes).*) $2 [L]
RewriteRule ^([_0-9a-zA-Z-]+/)?(.*\.php)$ $2 [L]
RewriteRule . index.php [L]

# END WordPress Multisite


id: 2fb83a9d5f694b6c8290485cb2778df2
parent_id: bc33dce65848438199af0fd3912185dd
created_time: 2025-04-15T07:51:00.934Z
updated_time: 2025-04-15T09:04:53.738Z
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
user_created_time: 2025-04-15T07:51:00.934Z
user_updated_time: 2025-04-15T09:04:53.738Z
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