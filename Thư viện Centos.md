Thư viện Centos

Thư viện Centos

To resolve the issue you can mass update all .repo files on centos 7:

sed -i s/mirror.centos.org/vault.centos.org/g /etc/yum.repos.d/CentOS-Base.repo  
sed -i s/^#.\\\*baseurl=http/baseurl=http/g /etc/yum.repos.d/CentOS-Base.repo  
sed -i s/^mirrorlist=http/#mirrorlist=http/g /etc/yum.repos.d/CentOS-Base.repo

yum update -y

nếu lỗi  
<br/>

sudo nano /etc/resolv.conf  
Thêm vào nội dung sau (hoặc thay thế nếu đã có):

nginx  
Copy  
Edit  
nameserver 8.8.8.8  
nameserver 1.1.1.1  
Đây là DNS của Google và Cloudflare – rất ổn định.

Lưu lại bằng Ctrl + O, Enter, rồi thoát Ctrl + X.

🧪 Bước 2: Kiểm tra lại  
Thử ping một tên miền:

bash  
Copy  
Edit  
ping google.com -c 4  
Nếu ping được → DNS đã hoạt động.

🔁 Bước 3: Thử lại yum  
bash  
Copy  
Edit  
yum clean all  
yum makecache  
yum update

id: 4d398a4c87c24c4fb0fda00f06c495ba
parent_id: bc33dce65848438199af0fd3912185dd
created_time: 2025-04-15T07:30:56.120Z
updated_time: 2025-06-13T01:54:46.535Z
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
user_created_time: 2025-04-15T07:30:56.120Z
user_updated_time: 2025-06-13T01:54:46.535Z
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