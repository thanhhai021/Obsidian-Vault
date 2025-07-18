Cài Virtualizor +Promox

Virtualizor +Promox

\\-------------------------------  
cài promox-virtualizor

cài nhớ để 0 phần swap và mvz  
promox ip:8006  
viturlizor ip:8005

Cài proxmox trên linux  
nhớ xem đã cài card mạng nào  
\\-check disk:  
    lsblk  
\\-định dạng ổ đĩa:  
    lvresize --extents +100%FREE --resizefs /dev/pve/root  
\\-Nano các file và thêm link download:  
    +nano /etc/apt/sources.list.d/pve-enterprise.list  
Add: deb http://download.proxmox.com/debian/pve bookworm pve-no-subscription  
    +nano /etc/apt/sources.list.d/ceph.list  
Add: #deb http://download.proxmox.com/debian/ceph-quincy bookworm no-subscription  
\\-Update:  
    apt update -y  
    apt --fix-broken install --Sửa gói bị lỗi  
    apt install unzip -y -- chạy các gói unzip  
    apt install parted screen net-tools -y -- cài các gói công cụ  
    screen --chạy 1 tiến trình mới riêng biệt  
    wget -N http://files.virtualizor.com/install.sh --Tải virtual  
    chmod +x install.sh -- cấp quyền thực thi để cài  
Cài: ./install.sh email=kythuat@megahost.vn kernel=proxmox license=VIRTE-80367-83284-46673-91844

fix lỗi raid sdb: mdadm --stop /dev/md127  
                    mdadm --zero-superblock /dev/sdb  
\\-Chuyển chuẩn password:  
    nano /etc/pam.d/common-password  
Edit:  
password \\\[success=1 default=ignore\\\] pam_unix.so obscure yescrypt  
To:  
password \\\[success=1 default=ignore\\\] pam_unix.so obscure sha512

\\-Update password root:passwd root

Test truy cập web contrl và login bằng user root  
https://192.168.1.192:4085/

Format ổ đĩa : parted -s /dev/sde mklabel gpt (ổ chứa hđh)  
vào Proxmox tạo raid cho ổ đĩa  
Truy cập vào web:8006 của Proxmox VE > Data Center > pve > Disks. Tại đây đang show ra toàn bộ ổ cứng đang chạy của hệ thống.  
Tiến hành cấu hình RaidZ-1 cho 4 ổ trống sdb-sdc-sdd-sde.  
VPS>Storage>ZFS>Add

⦁ Truy cập Proxmox add storage:  
https://192.168.1.205:8006/

đặt lại thông số: zfs set atime=off megahost  
                    zfs set xattr=sa megahost  
chép  
vi /etc/modprobe.d/zfs.conf  
    options zfs zfs_arc_min=8589934592  
    options zfs zfs_arc_max=17179869184

ghi  
    echo "$\\\[8 \\\* 1024\\\*1024\\\*1024 - 1\\\]" >/sys/module/zfs/parameters/zfs_arc_min     echo "$\\\[16 \\\* 1024\\\*1024\\\*1024\\\]" >/sys/module/zfs/parameters/zfs_arc_max  
    update-initramfs -u -k all

&nbsp;

Fix lỗi growpark khi cài OS windown trên Virtual  
apt install cloud-utils -y  
apt install cloud-guest-utilslsblk  
apt-get install chntpw

Virtualizor: https://192.168.1.192:4085/

Virtualizor  
    Khai báo hostname, password proxmox và Network interface to vitualizor:  
    Truy cập control để add storage:  
    Add node to master

Get server API password for node server:  
Cần allow ip cho node trên master  
Tạo thư mục backup -- mkdir /backup  
format ổ cứng backup -- mkfs.ext4 /dev/sdX1

&nbsp;

Gắn kết vào fstab: nano /etc/fstab  
            coppy: EX: UUID=4bfb69f2-bd25-4c4e-bf1d-d307b778dac2 /backup ext4 defaults 1 0

&nbsp;                   mount -a -- gắn kết các mục trong ftab  
                    systemctl daemon-reload  
                    df -h --kiểm tra dung lượng các disk đang dùng

&nbsp;

&lt;br/&gt;

Add storage + config backup cho proxmox  
Storage>Add>>Directory>Chọn VZdumpfile  
Backup>>General>>Retension>>Advanced(Stick repeat miss)

&nbsp;   Tạo IP pool -- Chỉnh các node dùng chung dải ip

&nbsp;   Tạo Plan -- Chỉnh plan dùng dải ip

&nbsp;   Add cfs:  
    Mở nano /etc/csf/csf.dyndns  
            virtualizor.com  
            softaculous.com

&nbsp;72f11896-f634-4b42-90a8-5209e733daeb /backup ext4 defaults 1 0

&nbsp;Add storage cho proxmox  
    Data center>Add  
    ID:backup  
    URL:/backup  
    VZDump File backup

Add config backup  
    Data center>Add  
    srorage:backup  
    Mode All  
    Email to (Email KH)  
    Mode Snapshot  
    Retension: Keep last 2  
    Avandce : Stick Repeat miss

Create IP Pool

&nbsp;

server r640 khi gắn ssd có thể sẽ không nhận ổ phải vào config auto raid clear convert về để nhận ổ cứng (do nhận ssd qua card raid)

id: bc12da1d610b475d89f0edff42c2cd5b
parent_id: bc33dce65848438199af0fd3912185dd
created_time: 2025-04-15T08:40:06.834Z
updated_time: 2025-06-04T08:43:08.089Z
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
user_created_time: 2025-04-15T08:40:06.834Z
user_updated_time: 2025-06-04T08:43:08.089Z
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