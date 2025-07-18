ký clickonce 

### **BƯỚC 1: Cài đặt SafeNet Authentication Client**

1.  Tải SafeNet Authentication Client từ GlobalSign:  
    👉 https://support.globalsign.com/
    
2.  Cài đặt và cắm USB token.
    
3.  Mở ứng dụng “SafeNet Authentication Client Tools” → vào **“Certificates”** → kiểm tra chứng chỉ xuất hiện là OK.
    

* * *

### 🔹 **BƯỚC 2: Lấy thông tin chứng chỉ từ token**

Mở PowerShell/cmd, chạy:

cmd

CopyEdit

`certutil -store My`

Tìm đến dòng có **Subject = ... GlobalSign ...**, ghi lại `Serial Number` hoặc `Subject`.

* * *

### 🔹 **BƯỚC 3: Publish ClickOnce không ký trước**

1.  Trong Visual Studio:
    
    - Chuột phải project → **Publish**
        
    - Chọn **“Folder”** hoặc **“File Share”** (không chọn Web Deploy).
        
    - Tạm **bỏ tích “Sign the ClickOnce manifests”** để publish ra file `.application` và `.manifest` chưa ký.
        

* * *

### 🔹 **BƯỚC 4: Ký tay manifest và deployment**

Giả sử output của bạn nằm ở thư mục `publish\`.

Bạn cần dùng công cụ `mage.exe` đi kèm với .NET SDK hoặc Visual Studio. Nếu chưa có, bạn có thể tìm trong:

bash

CopyEdit

`C:\Program Files (x86)\Microsoft SDKs\ClickOnce\SignTool\`

#### Ký Application Manifest

cmd

CopyEdit

`mage.exe -Sign "publish\YourApp.exe.manifest" -CertFile "C:\path\to\dummy.cer" -Password "" -TimeStampUri http://timestamp.globalsign.com/scripts/timstamp.dll`

⚠️ **Thay vì `-CertFile`, bạn nên dùng `-CSP` và `-KeyContainer` cho token**, ví dụ:

cmd

CopyEdit

`mage.exe -Sign "publish\YourApp.exe.manifest" ^ -CertHash [Mã SHA1 hash của cert từ certutil] ^ -CryptoProvider "eToken Base Cryptographic Provider" ^ -TimeStampUri http://timestamp.globalsign.com/scripts/timstamp.dll`

📌 Để lấy SHA1 Hash:

cmd

CopyEdit

`certutil -store My`

Tìm dòng: `Cert Hash(sha1): A1B2C3...`

#### Ký Deployment Manifest

cmd

CopyEdit

`mage.exe -Update "publish\YourApp.application" -AppManifest "publish\YourApp.exe.manifest" -CertHash [Hash của cert] -CryptoProvider "eToken Base Cryptographic Provider" -TimeStampUri http://timestamp.globalsign.com/scripts/timstamp.dll`

id: e42b6bc3990c47f48213881d99fef895
parent_id: ec70f7b8abf04c5eb248f465c2d794dc
created_time: 2025-07-17T03:19:45.405Z
updated_time: 2025-07-17T03:19:55.007Z
is_conflict: 0
latitude: 10.81058310
longitude: 106.70914220
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
user_created_time: 2025-07-17T03:19:45.405Z
user_updated_time: 2025-07-17T03:19:55.007Z
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