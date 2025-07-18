Fix lỗi trong file functions.php

  
$DomainRun = $\_SERVER\["SERVER_NAME"\];  
$runDomainName = 'https://' . $DomainRun . $\_SERVER\["REQUEST_URI"\];

if ($\_SERVER\["HTTPS"\] == "on") {  
    header("HTTP/1.1 301 Moved Permanently");  
    header("Location: $runDomainName");  
    exit();  
}

id: 20ea54cb6dba4192b7d0cdeb9303cb6e
parent_id: bc33dce65848438199af0fd3912185dd
created_time: 2025-04-15T07:01:38.371Z
updated_time: 2025-04-15T07:04:15.216Z
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
user_created_time: 2025-04-15T07:01:38.371Z
user_updated_time: 2025-04-15T07:04:15.216Z
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