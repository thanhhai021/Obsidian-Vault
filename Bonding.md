Bonding

&nbsp;

- # 1\. Kiến thức nền tảng
    
    **Bonding** cho phép bạn gộp nhiều card mạng thành 1 interface ảo.
    
- Có nhiều mode bonding, phổ biến nhất:
    
    - `mode=0` (balance-rr): luân phiên gửi gói (tăng băng thông).
        
    - `mode=1` (active-backup): 1 NIC chính, dự phòng NIC khác.
        
    - `mode=4` (802.3ad): LACP, yêu cầu switch hỗ trợ.
        

* * *

# 2\. Ví dụ cấu hình bonding trên Debian/Ubuntu/Proxmox (dùng `/etc/network/interfaces`)

Giả sử bạn có 2 NIC là `eno1` và `eno2`, muốn tạo bonding `bond0` ở mode 1 (dự phòng):

`auto bond0iface bond0 inet static address 192.168.1.100 netmask 255.255.255.0 gateway 192.168.1.1 bond-mode 1 bond-miimon 100 bond-slaves eno1 eno2`

Phần còn lại, bạn **bỏ cấu hình IP trên `eno1` và `eno2`**, chỉ cấu hình slave:

`iface eno1 inet manual bond-master bond0iface eno2 inet manual bond-master bond0`

* * *

# 3\. Giải thích

- `bond-mode 1`: active-backup (1 NIC chính, 1 dự phòng)
    
- `bond-miimon 100`: kiểm tra link mỗi 100ms để phát hiện lỗi
    
- `bond-slaves eno1 eno2`: 2 card mạng tham gia bonding
    

* * *

# 4\. Khởi động lại networking

`systemctl restart networking`

Hoặc khởi động lại máy.

* * *

# 5\. Kiểm tra trạng thái bonding

`cat /proc/net/bonding/bond0`

Bạn sẽ thấy trạng thái, mode và các slave.

* * *

# 6\. Nếu dùng mode 4 (LACP) với switch hỗ trợ

Cấu hình tương tự, chỉ khác mode:

`bond-mode 4bond-miimon 100bond-lacp-rate 1bond-slaves eno1 eno2`

Switch phải enable LACP cho 2 port đó.

* * *

Bonding interface file  
<br/>

auto lo  
iface lo inet loopback

auto eno1  
iface eno1 inet manual  
    bond-master bond0

iface eno2 inet manual  
    bond-master bond0

auto bond0  
iface bond0 inet static  
    address 10.0.1.20  
    netmask 255.255.255.0  
    gateway 10.0.1.1  
    dns-nameservers 8.8.8.8 8.8.4.4  
    bond-slaves enp2s0 enp3s0  
    bond-mode 802.3ad  
    bond-miimon 100  
    bond-downdelay 200  
    bond-updelay 200  
    bond-xmit-hash-policy layer3+4

source /etc/network/interfaces.d/\*

  
<br/>

id: dbf6d3df6cf64af3a9c647f3b42990dd
parent_id: bc33dce65848438199af0fd3912185dd
created_time: 2025-06-06T01:32:02.583Z
updated_time: 2025-06-10T01:32:59.934Z
is_conflict: 0
latitude: 10.82309890
longitude: 106.62966380
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
user_created_time: 2025-06-06T01:32:02.583Z
user_updated_time: 2025-06-10T01:32:59.934Z
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