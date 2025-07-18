Gửi mail bị lỗi 550 hoặc 554 (Relay access denied / not allowed)

## **Gửi mail bị lỗi 550 hoặc 554 (Relay access denied / not allowed)**

**Nguyên nhân:**

- Chưa bật `smtpd_sasl_auth_enable`.
    
- Mail client không dùng xác thực SMTP.
    
- Domain gửi không có trong `mydestination` hoặc `virtual_mailbox_domains`.
    

**Cách xử lý:**

Trong `/etc/postfix/main.cf`:

`smtpd_sasl_auth_enable = yessmtpd_recipient_restrictions = permit_sasl_authenticated, reject_unauth_destination`

Restart Postfix:

`systemctl restart postfix`

id: d89fd71e1bed4be987ebe9a5af5b2036
parent_id: bc33dce65848438199af0fd3912185dd
created_time: 2025-04-22T09:37:01.562Z
updated_time: 2025-04-23T07:37:47.198Z
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
user_created_time: 2025-04-22T09:37:01.562Z
user_updated_time: 2025-04-23T07:37:47.198Z
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