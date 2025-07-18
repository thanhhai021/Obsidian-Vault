Script .htaccess cho WordPress Multisite

### `.htaccess` cho WordPress Multisite (Subdomain):

\# BEGIN WordPress Multisite  
\# Using subdomain network type: https://wordpress.org/documentation/article/htaccess/#multisite

RewriteEngine On  
RewriteRule .\* - \[E=HTTP_AUTHORIZATION:%{HTTP:Authorization}\]  
RewriteBase /  
RewriteRule ^index\\.php$ - \[L\]

\# add a trailing slash to /wp-admin  
RewriteRule ^wp-admin$ wp-admin/ \[R=301,L\]

RewriteCond %{REQUEST_FILENAME} -f \[OR\]  
RewriteCond %{REQUEST_FILENAME} -d  
RewriteRule ^ - \[L\]  
RewriteRule ^(wp-(content|admin|includes).\*) $1 \[L\] RewriteRule ^(.\*\\.php)$

KaTeX parse error: Undefined control sequence: \\\[ at position 3: 1 \\̲\[̲L\\\] RewriteRu…

$1 \[L\]  
RewriteRule . index.php \[L\]

\# END WordPress Multisite

&nbsp;

id: 35e4689fc7574b4d993a104c32c21183
parent_id: bc33dce65848438199af0fd3912185dd
created_time: 2025-04-15T07:41:32.582Z
updated_time: 2025-04-15T08:55:33.347Z
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
user_created_time: 2025-04-15T07:41:32.582Z
user_updated_time: 2025-04-15T08:55:33.347Z
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