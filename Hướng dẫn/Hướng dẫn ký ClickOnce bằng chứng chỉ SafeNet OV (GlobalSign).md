Hướng dẫn ký ClickOnce bằng chứng chỉ SafeNet OV (GlobalSign)

## **Hướng dẫn ký ClickOnce bằng chứng chỉ SafeNet OV (GlobalSign)**

### 🔹 **Bước 1: Cài SafeNet Authentication Client**

- Tải và cài bản mới nhất từ GlobalSign hoặc Thales.
    
- Cắm USB token, đăng nhập vào SafeNet để đảm bảo nhận token và hiển thị chứng chỉ bên trong.
    

* * *

### 🔹 **Bước 2: Mở Visual Studio và cấu hình Publish**

1.  Mở project của bạn.
    
2.  Vào **Project > Properties > Publish**.
    
3.  Chọn **“Signing”** hoặc tab liên quan (tùy version Visual Studio).
    
4.  Tick **"Sign the ClickOnce manifests"** ✅
    

* * *

### 🔹 **Bước 3: Chọn chứng chỉ từ Token**

1.  Nhấn **"Select from Store"**.
    
2.  Một cửa sổ chọn chứng chỉ sẽ hiện ra.
    
3.  Chọn chứng chỉ có tên do **GlobalSign cung cấp** (VD: “GlobalSign CodeSigning CA - SHA256 - G3”).
    
    - Lưu ý: Đây **không phải file .pfx**, mà là **chứng chỉ từ store** do SafeNet export tạm thời để dùng.
        
    - Không nên tạo file .pfx từ token (vi phạm bảo mật).
        

* * *

### 🔹 **Bước 4: Cấu hình Timestamp Server**

- Điền vào ô timestamp:
    
    arduino
    
    CopyEdit
    
    `http://timestamp.digicert.com`
    
    hoặc
    
    arduino
    
    CopyEdit
    
    `http://tsa.globalsign.com`
    
- Timestamp giúp tránh lỗi "mất trust" khi chứng chỉ hết hạn.
    

* * *

### 🔹 **Bước 5: Publish Project**

- Nhấn **Publish** như bình thường.
    
- Visual Studio sẽ gọi `mage.exe` hoặc `signtool.exe` nội bộ để:
    
    - Sign file `.manifest` và `.application`.
        
    - Gắn timestamp.
        
    - Gọi token để xác thực (sẽ yêu cầu nhập mật khẩu token nếu chưa cache).

id: 341ec12a7b0344a9ac7b676112f4d94a
parent_id: ec70f7b8abf04c5eb248f465c2d794dc
created_time: 2025-07-17T03:26:31.651Z
updated_time: 2025-07-17T03:28:36.810Z
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
user_created_time: 2025-07-17T03:26:31.651Z
user_updated_time: 2025-07-17T03:28:36.810Z
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