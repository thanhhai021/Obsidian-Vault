CPanel / CyberPanel không truy cập được

## **CPanel / CyberPanel không truy cập được**

**Nguyên nhân:**

- Dịch vụ panel bị dừng.
    
- Cổng bị chặn (Firewall).
    
- Bị IP block do fail login nhiều lần.
    

**Cách khắc phục:**

- Restart service:  
    Ví dụ CyberPanel: `systemctl restart lscpd`  
    Hoặc: `systemctl restart cyberpanel`
    
- Mở port trên firewall:  
    `firewall-cmd --permanent --add-port=8090/tcp`  
    `firewall-cmd --reload`
    
- Kiểm tra IP block: vào `/etc/csf/csf.deny` hoặc log của Fail2Ban.

id: 86e61bfce0ec4d8f9f3773b6cb93067f
parent_id: bc33dce65848438199af0fd3912185dd
created_time: 2025-04-22T09:24:34.541Z
updated_time: 2025-04-22T09:24:39.715Z
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
user_created_time: 2025-04-22T09:24:34.541Z
user_updated_time: 2025-04-22T09:24:39.715Z
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