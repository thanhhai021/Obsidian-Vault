Serial yubikey 5 NFC FIPS Firmware 5.4.2 Serial: 17049915

![663f0a823a8b9509e81f55d735481729.png](:/6819e6edf2b045498bdc0501d5d438f3)

![f8bdb7de9f4c712addb87ca3a8790c35.png](:/cae67f86dba64d47b9bc243b0971d152)

&nbsp;

cd "C:\\Program Files\\Yubico\\YubiKey Manager"

.\\ykman.exe piv keys attest 9a ATTESTATION-VCS.crt  
.\\ykman.exe piv certificates export f9 INTERMEDIATE-VCS.crt

Mở certmgr.msc> tìm subject>

ký signtool

&nbsp;cd "C:\\Users\\huynh\\HelloSigner\\bin\\Release\\net9.0\\HelloSigner.exe"  
<br/>.\\signtool.exe sign /fd sha256 /tr http://ts.ssl.com /td sha256 /n "CÔNG TY CỔ PHẦN CÔNG NGHỆ VCS VIỆT NAM" "C:\\Users\\huynh\\HelloSigner\\bin\\Release\\net9.0\\HelloSigner.exe"  
<br/>

lệnh xóa slot:

ykman piv keys delete 9a  
ykman piv certificates delete 9a

id: 5ad0825d9b8f4c0f92a32caa4ee1098f
parent_id: ec70f7b8abf04c5eb248f465c2d794dc
created_time: 2025-05-16T06:25:17.505Z
updated_time: 2025-05-19T09:21:07.040Z
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
user_created_time: 2025-05-16T06:25:17.505Z
user_updated_time: 2025-05-19T09:21:07.040Z
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