Mail bị vào SPAM (Gmail, Outlook)

## **Mail bị vào SPAM (Gmail, Outlook)**

**Nguyên nhân:**

- Thiếu SPF, DKIM, DMARC.
    
- Không có PTR (rDNS).
    
- Nội dung giống spam (quảng cáo, link rút gọn).
    

**Cách xử lý:**

- Kiểm tra DNS:
    
    - SPF: `v=spf1 a mx ip4:x.x.x.x ~all`
        
    - DKIM: dùng OpenDKIM + thêm bản ghi DNS.
        
    - DMARC: `v=DMARC1; p=none; rua=mailto:you@example.com`
        
- Check spam score:
    
    - https://mail-tester.com
        
    - https://mxtoolbox.com

id: ff0be8851182471995f4bf57c18f5e76
parent_id: bc33dce65848438199af0fd3912185dd
created_time: 2025-04-22T09:36:51.208Z
updated_time: 2025-04-23T07:35:51.397Z
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
user_created_time: 2025-04-22T09:36:51.208Z
user_updated_time: 2025-04-23T07:35:51.397Z
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