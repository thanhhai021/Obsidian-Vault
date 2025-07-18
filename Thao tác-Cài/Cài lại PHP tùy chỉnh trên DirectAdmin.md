Build lại PHP tùy chỉnh trên DirectAdmin

### **Build lại PHP tùy chỉnh trên DirectAdmin**

#### 1\. **Kiểm tra phiên bản hiện tại**

`vi /usr/local/directadmin/custombuild/options.conf`

> Kiểm tra phiên bản PHP hiện tại trong file `options.conf` hoặc `version.txt`.

* * *

#### 2\. **Thay đổi phiên bản PHP muốn cài**

`cd /usr/local/directadmin/custombuildnano options.conf`

> Tìm dòng có tên `php1_release`, `php2_release`,... và sửa thành phiên bản PHP mong muốn (ví dụ `8.1` hoặc `8.2`).

* * *

#### 3\. **Cập nhật và build lại**

`./build update./build php n./build rewrite_confs`
