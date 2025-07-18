Cài SSL LE cho Mail Kerio:

SSL LE cho Kerio:  
sed -i s/mirror.centos.org/vault.centos.org/g /etc/yum.repos.d/CentOS-Base.repo  
sed -i s/^#.\\\*baseurl=http/baseurl=http/g /etc/yum.repos.d/CentOS-Base.repo  
sed -i s/^mirrorlist=http/#mirrorlist=http/g /etc/yum.repos.d/CentOS-Base.repo  
yum install epel-release  
yum install certbot  
service kerio-connect stop  
certbot certonly --standalone --preferred-challenges http -d mail.fastimex.vn  
File key mới tạo sẽ được lưu tại đường dẫn:  
 /etc/letsencrypt/live/mail.webnow.vn/  
Sau đó tải 2 file cert.pem và privkey.pem về máy rồi đổi tên lần lượt thành domain.crt và private.key  
service kerio-connect start  
Tiếp đến truy cập vào Kerio admin để import 2 key này vào.

id: fa26a1a64af64553a1a6ee334ab8d6fc
parent_id: bc33dce65848438199af0fd3912185dd
created_time: 2025-04-15T07:36:56.726Z
updated_time: 2025-04-23T07:17:25.923Z
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
user_created_time: 2025-04-15T07:36:56.726Z
user_updated_time: 2025-04-23T07:17:25.923Z
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