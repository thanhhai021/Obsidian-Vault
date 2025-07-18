Fix lỗi ssl web NINA

lỗi ssl web NINA

fix lỗi file function.php thành

$DomainRun=$\\\_SERVER\\\["SERVER_NAME"\\\];  
$runDomainName='https://'.$DomainRun.$\_SERVER\["REQUEST_URI"\]; if ($\\\_SERVER\\\["HTTPS"\\\] == "on") {  
header("HTTP/1.1 301 Moved Permanently");  
header("Location: $runDomainName")

Fix lỗi file htaccess

RewriteEngine On  
RewriteCond %{HTTPS} off  
RewriteRule ^ https://%{HTTP_HOST}%{REQUEST_URI} \[L,R=301\]

id: a69e065caf8c42719c7c0b8e7eafc9f9
parent_id: bc33dce65848438199af0fd3912185dd
created_time: 2025-04-15T07:29:15.260Z
updated_time: 2025-04-15T09:03:50.687Z
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
user_created_time: 2025-04-15T07:29:15.260Z
user_updated_time: 2025-04-15T09:03:50.687Z
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