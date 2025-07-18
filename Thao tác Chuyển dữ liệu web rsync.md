Thao tác Chuyển dữ liệu web rsync

Chuyển dữ liệu web rsync

Chuyển dữ liệu web

kiểm tra dung lượng backup  
kiểm tra dung lượng ổ đĩa  
đăng nhập admin web cần chuyển  
chạy backup trên host cũ  
kiểm tra tiến trình backup top -c  
test mail thành công  
vào root linux kiểm tra cpu xem đã chạy chưa: top -c  
cài các repo cần để chuyển dữ liệu  
sed -i s/mirror.centos.org/vault.centos.org/g /etc/yum.repos.d/CentOS-Base.repo  
sed -i s/^#.\*baseurl=http/baseurl=http/g /etc/yum.repos.d/CentOS-Base.repo  
sed -i s/^mirrorlist=http/#mirrorlist=http/g /etc/yum.repos.d/CentOS-Base.repo  
yum install rsync -y  
chạy Lệnh bắt đầu sync trên host cũ đến host mới (nhớ đặt lại ip của hostcaanf chuyển đến ip host mới  
rsync -avz -e "ssh -p 22" --progress /home/admin/admin_backups/\* root@103.161.173.103:/home/admin/admin_backups/  
vao nano /etc/my.cnf copy dong sql-mode="NO_ENGINE_SUBSTITUTION" tu host cu sang host moi

id: 9fc35212210a41538839697c1fcbd577
parent_id: bc33dce65848438199af0fd3912185dd
created_time: 2025-04-15T07:19:28.302Z
updated_time: 2025-04-15T08:57:51.037Z
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
user_created_time: 2025-04-15T07:19:28.302Z
user_updated_time: 2025-04-15T08:57:51.037Z
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