Cài JetBackup 5 cho DirectAdmin

## Cài đặt JetBackup 5 cho DirectAdmin

### Trước khi chạy lệnh cài:

**Chỉnh sửa lại file repo "Base-Centos"** (có thể là `/etc/yum.repos.d/CentOS-Base.repo`) để bật/tắt repo cần thiết.

### Lệnh cài đặt:

`yum install jetbackup5-directadmin -y \--disablerepo=* \--enablerepo=base,cloudlinux-base,cloudlinux-x86_64-server-7,jetapps,jetapps-stable`

* * *

## Kiểm tra ổ đĩa sau khi cài OS

Chạy lệnh:

`lsblk -f`
