Cài đặt Zabbix Server trên AlmaLinux

### **1\. Cài đặt Zabbix Server trên AlmaLinux**

#### Bước 1: Cài đặt kho lưu trữ Zabbix

Đầu tiên, cần thêm kho lưu trữ của Zabbix vào hệ thống:

bash

CopyEdit

`dnf install https://repo.zabbix.com/zabbix/6.4/rhel/9/x86_64/zabbix-release-6.4-1.el9.noarch.rpm`

#### Bước 2: Cài đặt các gói cần thiết

Cài đặt **Zabbix server, web frontend, database scripts**:

bash

CopyEdit

`dnf install zabbix-server-mysql zabbix-web-mysql zabbix-appliance zabbix-sql-scripts`

#### Bước 3: Cài đặt và cấu hình MariaDB (MySQL) làm cơ sở dữ liệu

Cài đặt MariaDB (nếu chưa có):

bash

CopyEdit

`dnf install mariadb-server`

Khởi động và cấu hình MariaDB:

bash

CopyEdit

`systemctl start mariadbsystemctl enable mariadb`

Cấu hình MariaDB (nếu cần):

bash

CopyEdit

`mysql_secure_installation`

Tạo database và người dùng cho Zabbix:

bash

CopyEdit

`mysql -u root -pCREATE DATABASE zabbix CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci;GRANT ALL PRIVILEGES ON zabbix.* TO 'zabbix'@'localhost' IDENTIFIED BY 'your_password';FLUSH PRIVILEGES;EXIT;`

#### Bước 4: Cấu hình Zabbix Server

Chỉnh sửa file cấu hình của Zabbix Server:

bash

CopyEdit

`vi /etc/zabbix/zabbix_server.conf`

Tìm các mục sau và thay đổi:

`DBHost=localhostDBName=zabbixDBUser=zabbixDBPassword=your_password`

#### Bước 5: Cài đặt Zabbix Frontend (Web Interface)

Cài đặt Apache và PHP:

`dnf install httpd php php-mysqli php-gd php-xml php-bcmath`

Khởi động và cấu hình Apache:

`systemctl start httpdsystemctl enable httpd`

Chỉnh sửa file cấu hình PHP (nếu cần):

`vi /etc/php.ini`

Điều chỉnh các giá trị sau:

`date.timezone = Asia/Ho_Chi_Minhmax_execution_time = 300memory_limit = 128M`

#### Bước 6: Khởi động Zabbix Server

Khởi động và kích hoạt Zabbix Server:

`systemctl start zabbix-serversystemctl enable zabbix-server`

#### Bước 7: Cấu hình và kiểm tra Zabbix Frontend

Truy cập vào Zabbix Web Interface:

`http://your-server-ip/zabbix`

Hoàn tất quá trình cấu hình bằng cách cung cấp thông tin về database, tài khoản người dùng và các cài đặt cần thiết.

### **2\. Cài đặt Zabbix Agent trên máy giám sát**

Trên mỗi máy chủ cần giám sát, bạn cần cài đặt **Zabbix Agent**:

`dnf install zabbix-agent`

Chỉnh sửa file cấu hình Zabbix Agent:

`vi /etc/zabbix/zabbix_agentd.conf`

Cấu hình các mục sau:

`Server=ZABBIX_SERVER_IPHostname=your-hostname`

Khởi động và kích hoạt Zabbix Agent:

`systemctl start zabbix-agentsystemctl enable zabbix-agent`

### **3\. Các lỗi thường gặp và cách khắc phục**

#### Lỗi 1: **Không thể kết nối tới database**

Lỗi: `Access denied for user 'zabbix'@'localhost' (using password: YES)`

**Cách khắc phục**:

- Kiểm tra lại quyền truy cập của người dùng Zabbix đối với database:
    
    `SHOW GRANTS FOR 'zabbix'@'localhost';`
    
- Đảm bảo rằng người dùng Zabbix có quyền `ALL PRIVILEGES` trên database `zabbix`.
    

#### Lỗi 2: **Không thể tạo PID file cho Zabbix server**

Lỗi: `cannot create PID file [/run/zabbix/zabbix_server.pid]: [13] Permission denied`

**Cách khắc phục**:

- Kiểm tra quyền truy cập thư mục `/run/zabbix` và đảm bảo rằng Zabbix có quyền ghi vào thư mục đó:
    
    `chown -R zabbix:zabbix /run/zabbix`
    
- Sau đó, khởi động lại dịch vụ Zabbix Server:
    
    `systemctl restart zabbix-server`
    

#### Lỗi 3: **Không thể truy cập Web Interface của Zabbix**

Lỗi: `ERR_CONNECTION_TIMED_OUT`

**Cách khắc phục**:

- Kiểm tra cấu hình firewall và đảm bảo rằng cổng 80 (HTTP) hoặc 443 (HTTPS) mở:
    
    `firewall-cmd --permanent --add-service=httpfirewall-cmd --reload`
    

#### Lỗi 4: **Không thể tạo các bảng trong database**

Lỗi: `Table 'role' already exists`

**Cách khắc phục**:

- Kiểm tra nếu các bảng đã tồn tại trong cơ sở dữ liệu. Nếu các bảng đã tồn tại, bạn có thể xóa chúng và thử lại:
    
    `mysql -u zabbix -p zabbixDROP TABLE IF EXISTS role;`

id: 9db6659164714f97ba55ea521e066c71
parent_id: bc33dce65848438199af0fd3912185dd
created_time: 2025-04-16T06:59:04.987Z
updated_time: 2025-04-23T07:15:10.220Z
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
user_created_time: 2025-04-16T06:59:04.987Z
user_updated_time: 2025-04-23T07:15:10.220Z
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