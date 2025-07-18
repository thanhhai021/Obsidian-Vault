xóa key yubikey

## 🎯 Kết luận:

| Kiểm tra mục đích | Lệnh cần dùng |
| --- | --- |
| Reset sạch PIV | `yubico-piv-tool -a reset` |
| Kiểm tra slot có key không | `yubico-piv-tool -s 9a -a status` |
| Tạo key mới | `yubico-piv-tool -a generate -s 9a -A ECCP256 -o pubkey.pem` |
| So fingerprint key | `openssl pkey -pubin -in pubkey.pem -outform DER \| sha256sum` |
| Kiểm tra CSR cũ | `openssl req -in file.csr -noout -pubkey \| openssl pkey -pubin -outform DER \| sha256sum` |
| Kiểm tra attestation | `openssl x509 -in file.crt -noout -pubkey \| openssl pkey -pubin -outform DER \| sha256sum` |

id: 52d5b43bcff54670b4449655275f116d
parent_id: ec70f7b8abf04c5eb248f465c2d794dc
created_time: 2025-05-20T01:08:27.689Z
updated_time: 2025-05-20T01:08:38.240Z
is_conflict: 0
latitude: 10.82309890
longitude: 106.62966380
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
user_created_time: 2025-05-20T01:08:27.689Z
user_updated_time: 2025-05-20T01:08:38.240Z
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