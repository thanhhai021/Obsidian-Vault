yubikey

## Yubikey: Tạo chứng chỉ xác thực để cấp CodeSign

Để Chứng chỉ ký mã / CodeSign SSL được cấp, bạn cần tạo chứng chỉ xác thực gọi là **Attestation Certificate**

> Yêu cầu: Yubikey Manager được cài đặt trên máy, xem [hướng dẫn ở đây](https://muassl.com/vn/ho-tro/trung-tam-giai-dap/huong-dan-cai-dat/yubikey-cai-dat-yubikey-manager-va-smart-card.html)

\*\*Thực hiện như sau  
\*\*

#### Tạo mã CSR từ Yubikey Manager

1.  Mở \*\*Yubikey Manager  
    \*\*[![Yubikey: Tạo chứng chỉ xác thực để cấp CodeSign](:/08350bfb699b4f3897a88e719c61c59b "Yubikey: Tạo chứng chỉ xác thực để cấp CodeSign")](https://muassl.com/data/image/202307/377e57ace14031708ab0225a0043874f.png)
2.  Chọn mục **Applications > PIV**
3.  Chọn **Certificates -> Configure Certificates**
4.  Chọn mục **Authentication (Slot 9a)**
5.  Chọn **Generate**
6.  Chọn **Certificate Signing Request (CSR)**
7.  Chọn **Algorithm** với chế độ **ECCP384**  
    [![Yubikey: Tạo chứng chỉ xác thực để cấp CodeSign](:/c5f64d6349514ea0aab62e00a01e82da "Yubikey: Tạo chứng chỉ xác thực để cấp CodeSign")](https://muassl.com/data/image/202307/508a03ada3c8459baf3cb030eea79fcd.png)
8.  Nhập tên công ty của bạn trong mục **Subject**  
    [![Yubikey: Tạo chứng chỉ xác thực để cấp CodeSign](:/12a178b3bb4a45ce8c8df55de62e3950 "Yubikey: Tạo chứng chỉ xác thực để cấp CodeSign")](https://muassl.com/data/image/202307/40928362bc1cb3016641b38d9ee41e3b.png)
9.  Nhấp Next để chọn nơi lưu csr, sau đó bạn nhập **Management key** và **pin** để hoàn thành

> Chọn **Use defafault** nếu bạn chưa đổi **Management key**  
> Nhập **Pin**, mặc định là **123456** nếu bạn chưa đổi

#### Tạo chứng chỉ xác thực Attestation Certificate

Mở **Windows PowerShell** với chế độ **Administrator**

Di chuyển tới thư mục cài đặt **Yubikey Manager**, lệnh

- code
- source & copy

```
cd "C:\Program Files\Yubico\YubiKey Manager"
```

Tạo tập tin chứng chỉ **ATTESTATION**, chạy lệnh

- code
- source & copy

```
.\ykman.exe piv keys attest 9a ATTESTATION-FILENAME.crt
```

Tạo tập tin chứng chỉ **INTERMEDIATE**, lệnh

- code
- source & copy

```
.\ykman.exe piv certificates export f9 INTERMEDIATE-FILENAME.crt
```

Sau đó mở gửi 2 tập tin **ATTESTATION-FILENAME.crt** và **INTERMEDIATE-FILENAME.crt** tới support@muassl.com để xác thực

Sau khi hoàn thành xong, MuaSSL sẽ trả về bạn chứng chỉ **CodeSign** để bạn nhập vào **Yubikey**

id: 590b271d09d245a680e03d8ca91ec61c
parent_id: ec70f7b8abf04c5eb248f465c2d794dc
created_time: 2025-05-15T09:48:28.895Z
updated_time: 2025-06-02T08:55:37.224Z
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
user_created_time: 2025-05-15T09:48:28.895Z
user_updated_time: 2025-06-02T08:55:37.224Z
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