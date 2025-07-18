safenet

safenet  
eToken 5110 CC (940) với số serial 227623B04611EF2E đã được khởi tạo  
EV Codesigning của quý khách đã được khởi tạo với token có số serial là: 227623B04611EF2E  
\- Mật khẩu của Token là: Haoquangviet@  
\- Mã pin: Mặc định  
\- Mã Administrator: Mặc định  
<br/><br/>Bên dưới là thông tin của Token  
Token name: CONG TY TNHH VIETPN  
Token category: Hardware  
Reader name: SafeNet Token JC 0  
Serial number (PKCS#11): 227623B04611EF2E  
Free space (minimum estimated): 64461  
Card ID (GUID): 0x818000564682107A818000564682107A  
Product name: eToken 5110 CC (940)  
Card type: IDPrime  
Applet Version: IDPrime Java Applet 4.4.2.A  
Mask version: G286  
Token Password: Present  
Token Password retries remaining: 5  
Maximum Token Password retries: 15  
Token Password expiration: 30 days (30-Jul-2025)  
Administrator Password: Present  
Administrator Password retries remaining: 5  
Maximum administrator Password retries: 5  
FIPS: N/A  
Common Criteria (CC): CC EAL5+ / PP QSCD  
Token unlock objects: Administrator  
Digital Signature PIN retries remaining: 3  
Digital Signature PIN maximum retries: 3  
Digital Signature PUK retries remaining: 0  
Digital Signature PUK maximum retries: 3  
Sign padding on-board: Yes  
Supported key size: 4096 bits  
ECC: Supported  
CSP: eToken Base Cryptographic Provider  
KSP: SafeNet Smart Card Key Storage Provider

&nbsp;

&nbsp;

sigcode globalsign   
https://support.globalsign.com/code-signing/download-and-install-code-signing-certificate-hsm-based  
https://support.globalsign.com/code-signing/download-and-install-standard-code-signing-certificate  
<br/><br/><br/><br/>

Ký VStudio  
<br/>

## 🔹 **Bước 1: Cài SafeNet Authentication Client**

### ✅ Mục đích:

SafeNet Authentication Client (SAC) dùng để giao tiếp với USB Token (SafeNet eToken) chứa chứng chỉ số để ký mã.

### 📝 Các bước thực hiện:

1.  **Tải SafeNet Authentication Client (SAC)**
    
    - Truy cập: https://support.globalsign.com
        
    - Tìm theo từ khóa: `SafeNet Authentication Client`
        
    - Chọn bản phù hợp hệ điều hành (Windows 64-bit thường là lựa chọn phổ biến)
        
2.  **Cài đặt phần mềm SAC**
    
    - Mở file `.exe` đã tải về → **Next → Accept → Next → Install**
        
    - Sau khi cài xong, khởi động lại máy nếu được yêu cầu.
        
3.  **Cắm USB Token vào máy tính**
    
    - SAC sẽ nhận dạng USB Token, bạn sẽ thấy biểu tượng khóa vàng dưới taskbar.
        
    - Mở phần mềm SAC để xem thông tin Token:
        
        - Start → tìm "SafeNet Authentication Client Tools"
            
        - Vào tab **Tokens** → bạn sẽ thấy token chứa chứng chỉ GlobalSign
            

* * *

## 🔹 **Bước 2: Cài đặt Code Signing vào máy**

### ✅ Trường hợp 1: Bạn đã được cấp USB Token từ GlobalSign → KHÔNG cần cài chứng chỉ nữa

→ Chứng chỉ đã được cài sẵn trong USB

### ✅ Trường hợp 2: GlobalSign cấp chứng chỉ dạng `.p7b` hoặc `.cer` → Cần import vào token

#### 💡 Cách kiểm tra:

- Mở SAC Tool → **Certificates** → xem nếu đã có chứng chỉ GlobalSign thì bỏ qua bước này.

#### 🛠 Nếu **chưa có**, làm theo các bước:

1.  **Cắm token và mở SAC Tool**
    
2.  Mở chứng chỉ bạn nhận từ GlobalSign (thường là file `.p7b`)
    
3.  Nhấp chuột phải → Install Certificate
    
4.  Chọn **Store Location: Current User**
    
5.  Chọn **Place all certificates in the following store → Personal**
    
6.  Hoặc dùng phần mềm **"eToken PKI Client" hoặc "SAC Tool"** để **import chứng chỉ vào Token** (nếu có định dạng PFX, CER)
    

> 🔐 Nếu GlobalSign đã import sẵn thì bạn bỏ qua phần này.

* * *

## 🔹 **Bước 3: Cấu hình ký Code Signing trong ClickOnce (Visual Studio)**

### ✅ Mục tiêu:

Dùng chứng chỉ trong Token để **ký ClickOnce manifest** khi publish ứng dụng .NET.

### 📝 Các bước thực hiện:

#### 1\. **Mở Visual Studio → Mở project cần publish**

#### 2\. Vào phần cấu hình:

- Chuột phải vào project → **Properties**
    
- Vào tab **Signing**
    

#### 3\. **Tích chọn “Sign the ClickOnce manifests”**

- Nhấn **Select from Store…**
    
- Một cửa sổ hiện ra → chọn tab **Personal** → chọn **GlobalSign OV Code Signing Certificate** từ Token
    

> 💡 Nếu không thấy chứng chỉ:  
> Bạn cần mở Visual Studio **với quyền Administrator**, và đảm bảo SAC nhận token.

#### 4\. **Chọn thời gian timestamp**

- Trong tab **Publish** → nhấn nút **Options** → tab **Signing**
    
- Nhập timestamp server:
    
    arduino
    
    CopyEdit
    
    `http://timestamp.globalsign.com/scripts/timstamp.dll`
    
    Hoặc (mới hơn):
    
    arduino
    
    CopyEdit
    
    `http://timestamp.sectigo.com`
    

#### 5\. **Publish ứng dụng như bình thường**

- Khi click **Publish**, Visual Studio sẽ yêu cầu bạn nhập mã PIN của Token để ký

* * *

## ✅ Kiểm tra kết quả

Sau khi publish xong, bạn có thể:

- Click chuột phải vào file `.application` hoặc `.exe` → Properties → tab **Digital Signatures**
    
- Kiểm tra chứng chỉ: **Issued by GlobalSign**
    
- Xem mục timestamp nếu có

id: 69901052999145d3910a3a213efb6a0f
parent_id: ec70f7b8abf04c5eb248f465c2d794dc
created_time: 2025-07-10T01:05:53.445Z
updated_time: 2025-07-17T03:10:19.220Z
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
user_created_time: 2025-07-10T01:05:53.445Z
user_updated_time: 2025-07-17T03:10:19.220Z
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