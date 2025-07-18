Cài WP cent os 7

Cài WP

Cài Wordpress:  
    sudo yum update -y  
    sudo yum install wget -y  
    cd /tmp  
    wget https://wordpress.org/latest.tar.gz  
    tar -xvzf latest.tar.gz  
    sudo chown -R apache:apache /var/www/html/\*  
    sudo chmod -R 755 /var/www/html/\*  
    cd /var/www/html  
cp wp-config-sample.php wp-config.php  
Chỉnh sửa file wp-config.php:  
    nano wp-config.php

&nbsp;   define('DB_NAME', 'wordpress');  
    define('DB_USER', 'wpuser');  
    define('DB_PASSWORD', 'password');

id: 10411c02072c430a8993df2b99677b42
parent_id: bc33dce65848438199af0fd3912185dd
created_time: 2025-04-15T07:32:00.082Z
updated_time: 2025-04-15T08:54:28.806Z
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
user_created_time: 2025-04-15T07:32:00.082Z
user_updated_time: 2025-04-15T07:32:14.769Z
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