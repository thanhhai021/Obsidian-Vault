2IP trên 1 card

## ✅ `/etc/network/interfaces`:

Nội dung /etc/network/interfaces  
<br/>auto lo

iface lo inet loopback

&nbsp;

auto eno1

iface eno1 inet manual

bond-master bond0

&nbsp;

auto eno2

iface eno2 inet manual

bond-master bond0

&nbsp;

auto bond0

iface bond0 inet static

address 10.0.1.20

netmask 255.255.255.0

gateway 10.0.1.1

dns-nameservers 8.8.8.8 8.8.4.4

bond-mode balance-alb

bond-miimon 100

bond-slaves eno1 eno2  
<br/>

* * *

## ✅ Cần chỉnh thêm file `rt_tables` (nếu chưa có)

Mở `/etc/iproute2/rt_tables` và thêm 2 dòng ở cuối:

ini

CopyEdit

`100 rt10101 rt192`

* * *

## ✅ Reload cấu hình:

bash

CopyEdit

`ifdown bond0 && ifup bond0`

Hoặc:

bash

CopyEdit

`reboot`

