Fix install my sql

fix install my sql

fix install my sql  
sudo systemctl stop mariadb  
sudo mysqld_safe --skip-grant-tables &  
mysql -u root  
FLUSH PRIVILEGES;  
UPDATE mysql.user SET plugin = '', Password = PASSWORD('Hiepkhung1@') WHERE User = 'root' AND Host = 'localhost';  
UPDATE mysql.user SET authentication_string = '' WHERE User = 'root' AND Host = 'localhost';  
FLUSH PRIVILEGES;  
exit;  
sudo systemctl stop mariadb  
ps aux | grep mysql  
sudo kill -9 13660 13661 13810  
sudo rm -f /var/lib/mysql/mysql.sock  
sudo chown -R mysql:mysql /var/lib/mysql  
sudo systemctl start mariadb  
sudo systemctl status mariadb  
mysql -u root -p

id: ab5067c651774e55bd64f95f925779ad
parent_id: bc33dce65848438199af0fd3912185dd
created_time: 2025-04-15T08:37:32.516Z
updated_time: 2025-06-16T06:02:10.218Z
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
user_created_time: 2025-04-15T08:37:32.516Z
user_updated_time: 2025-06-16T06:02:10.218Z
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