Derbian

### 🛠 **1\. Cài đặt và khởi động SSH**

- Cài SSH server:
    
    bash
    
    CopyEdit
    
    `sudo apt install openssh-server -y`
    
- Bật dịch vụ SSH và kiểm tra:
    
    bash
    
    CopyEdit
    
    `sudo systemctl enable --now sshsudo systemctl status ssh`
    
- Kết nối SSH từ máy khác:
    
    bash
    
    CopyEdit
    
    `ssh root@192.168.0.19`
    
- Gặp lỗi đăng nhập: do sai mật khẩu hoặc cấu hình `sshd_config` chưa cho phép login `root`.
    

* * *

### ⚙️ **2\. Sửa lỗi APT dùng nguồn từ CD-ROM**

- Lỗi khi chạy `apt update` do dòng `cdrom:` trong `/etc/apt/sources.list`.
    
- Đã sửa bằng cách:
    
    - Mở file: `sudo nano /etc/apt/sources.list`
        
    - Comment dòng `cdrom:` lại bằng `#`.
        
    - Thêm các dòng repo chuẩn:
        
        plaintext
        
        CopyEdit
        
        `deb http://deb.debian.org/debian bookworm main contrib non-free non-free-firmwaredeb http://security.debian.org/debian-security bookworm-security main contrib non-freedeb http://deb.debian.org/debian bookworm-updates main contrib non-free`
        
- Sau đó chạy lại:
    
    bash
    
    CopyEdit
    
    `sudo apt update`
    

* * *

### 🔥 **3\. Cài và cấu hình tường lửa UFW**

- Cài UFW:
    
    bash
    
    CopyEdit
    
    `sudo apt install ufw -y`
    
- Cho phép SSH và bật tường lửa:
    
    bash
    
    CopyEdit
    
    `sudo ufw allow sshsudo ufw enable`
    
- Khi chạy `sudo ufw enable`, gặp lỗi `UnicodeDecodeError` do gõ tiếng Việt khi xác nhận `y/n`.
    
    - Đã khắc phục bằng cách tắt Unikey hoặc dùng lệnh:
        
        bash
        
        CopyEdit
        
        `sudo ufw --force enable`
        

* * *

### 💡 Trạng thái hiện tại:

- SSH đang chạy.
    
- APT cập nhật bình thường.
    
- Tường lửa UFW đã được bật và cho phép SSH.
    

* * *

Nếu bạn cần tiếp tục với cấu hình Nginx, PHP, Web server, hay muốn tôi tạo **script tổng hợp cài đặt & cấu hình hệ thống như đã làm** để dùng sau này, có thể yêu cầu tại đây.
