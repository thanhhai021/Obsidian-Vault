Fix lỗi update pass database DA

lỗi update pass database DA

lỗi update pass database  
Error change password user:  
Error altering user 'lppdcia9': View 'mysql.user' references invalid table(s) or column(s) or function(s) or definer/invoker of view lack rights to use them

Fix:  
add mysql_use_new_user_methods=1 on directadmin.conf

id: 49c1fd8fe33243308c1afb6c8a509245
parent_id: bc33dce65848438199af0fd3912185dd
created_time: 2025-04-15T07:54:09.026Z
updated_time: 2025-04-15T09:04:27.239Z
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
user_created_time: 2025-04-15T07:54:09.026Z
user_updated_time: 2025-04-15T09:04:27.239Z
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