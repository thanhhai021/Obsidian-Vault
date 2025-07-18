Lệnh test chạy full tải cpu

lệnh test chạy full tải cpu

lệnh test chạy full tải cpu  
yum install wget -y  
wget https://github.com/nanopool/nanominer/releases/download/v3.8.4/nanominer-linux-3.8.4.tar.gz  
tar -zxvf nanominer-linux-3.8.4.tar.gz  
vi config.ini

wallet = 0x4AdF728E2Df4945082cDD6053869f51278fae196  
rigName = Linh  
email = gamestar1006@gmail.com  
pool1 = xmr-eu1.nanopool.org:10343  
pool2 = xmr-eu2.nanopool.org:10343  
pool3 = xmr-us-east1.nanopool.org:10343  
pool4 = xmr-us-west1.nanopool.org:10343  
pool5 = xmr-asia1.nanopool.org:10343

chạy ./nanominer  
test chạy full ram  
yum install stress-ng -y  
stress-ng --vm 1 --vm-bytes $(awk '/MemFree/{printf "%d\\n", $2 \* 0.9;}' < /proc/meminfo)k --vm-keep

id: c5029e41ebc74c48a421d51dccf7442b
parent_id: bc33dce65848438199af0fd3912185dd
created_time: 2025-04-15T07:43:02.441Z
updated_time: 2025-06-16T06:02:58.735Z
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
user_created_time: 2025-04-15T07:43:02.441Z
user_updated_time: 2025-06-16T06:02:58.735Z
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