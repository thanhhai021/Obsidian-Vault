Thao tác chỉnh session kết nối Remote Desktop

chỉnh session kết nối Remote Desktop

chỉnh session kết nối Remote Desktop

Chỉnh sửa giá trị liên quan:( trên vps)

MaxIdleTime:

Chỉnh giá trị để ngăn việc ngắt session không hoạt động.  
Đường dẫn:

HKEY_LOCAL_MACHINE\\SYSTEM\\CurrentControlSet\\Control\\Terminal Server\\WinStations\\RDP-Tcp  
Tìm giá trị MaxIdleTime (nếu không tồn tại, tạo mới kiểu DWORD (32-bit)).  
Đặt giá trị 0 (Hexadecimal) để vô hiệu hóa timeout (giữ session mãi mãi).  
KeepAliveEnable:

Đảm bảo tính năng "Keep Alive" được bật để kết nối không bị mất.  
Đường dẫn:

HKEY_LOCAL_MACHINE\\SYSTEM\\CurrentControlSet\\Services\\Tcpip\\Parameters  
Tìm hoặc tạo mới giá trị KeepAliveTime (kiểu DWORD).  
Đặt thời gian (theo miliseconds, ví dụ: 300000 cho 5 phút).  
Khởi động lại máy:

Các thay đổi trong Registry cần khởi động lại để có hiệu lực.  
Thay đổi qua Group Policy (nếu cần)  
Mở Local Group Policy Editor:

Nhấn Win + R, gõ gpedit.msc, nhấn Enter.  
Điều hướng:

Computer Configuration -> Administrative Templates -> Windows Components -> Remote Desktop Services -> Remote Desktop Session Host -> Session Time Limits.  
Tùy chỉnh các thiết lập:

Set time limit for active but idle RDP sessions:  
Chọn Disabled để vô hiệu hóa giới hạn thời gian.  
Set time limit for disconnected sessions:  
Chọn thời gian hoặc Disabled để giữ session mãi mãi.  
Áp dụng thay đổi:

Nhấn OK, sau đó khởi động lại dịch vụ RDP:

net stop TermService && net start TermService

id: d4cb7290b44b4bfea9adbd43165c0bc4
parent_id: bc33dce65848438199af0fd3912185dd
created_time: 2025-04-15T08:41:52.685Z
updated_time: 2025-04-15T08:57:43.156Z
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
user_created_time: 2025-04-15T08:41:52.685Z
user_updated_time: 2025-04-15T08:57:43.156Z
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