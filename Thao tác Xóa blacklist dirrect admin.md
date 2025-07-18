Thao tác Xóa blacklist dirrect admin

Xóa blacklist dirrect admin

Xóa blacklist dirrect admin  
#cat /usr/local/directadmin/data/admin/ip_blacklist

Bước 3: Xóa toàn bộ danh sách IP blacklist của Directadmin.

#echo > /usr/local/directadmin/data/admin/ip_blacklist

Bước 4: Đưa IP của quý khách vào danh sách IP whitelist của Directadmin để không gặp lại tình trạng trên.

#echo "IP WAN" >> /usr/local/directadmin/data/admin/ip_whitelist

sửa ip:  
sudo nano /etc/sysconfig/network-scripts/ifcfg-eth0  
sudo systemctl restart network

xóa ip block trong csf: cat /etc/csf/csf.deny  
                        csf-a 171.236.211.116

id: 92051c68cfbb470397fb3d67e042237e
parent_id: bc33dce65848438199af0fd3912185dd
created_time: 2025-04-15T07:08:02.806Z
updated_time: 2025-04-15T09:07:05.310Z
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
user_created_time: 2025-04-15T07:08:02.806Z
user_updated_time: 2025-04-15T09:07:05.310Z
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