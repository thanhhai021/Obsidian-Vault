Cách cài SSL  mail mdaemon 

Mở CMD, chạy các lệnh bên dưới:

```
#Tải về định dang PFX (nếu có sẵn)`powershell -executionpolicy bypass -command "$client = new-object System.Net.WebClient;$client.Headers.Add(\"API-KEY\", \"FWgURQildSVc\");$client.DownloadFile(\"http://muassl.xyz/orders/params/action/getOrderDetails/order/M04182293/get/zip/pfx/tIaucDk7\",\"C:\M04182293.zip\");$client.DownloadFile(\"http://muassl.xyz/data/unzip.exe\",\"C:\unzip.exe\");$unzip=\"C:\unzip.exe\";$destination=\"C:\M04182293\";&$unzip \"C:\M04182293.zip\" -d $destination"`#Giải thích tham số:
#/get/pfx: Tải về định dạng PFX
#pfx/tIaucDk7: Đặt Mật khẩu của tập tin PFX là tIaucDk7
#"C:\M04182293.pfx => Tập tin sẽ lưu ở Ổ đĩa C với tên M04182293.pfx

#Nhập PFX vào máy chủ của bạn
`powershell -executionpolicy bypass -command "Import-PfxCertificate -Password (ConvertTo-SecureString -String \"tIaucDk7\" -AsPlainText -Force) -FilePath \"C:\M04182293\PFX\mail.kntvietnam.com.pfx\" -CertStoreLocation Cert:\LocalMachine\My -Exportable"`
```

id: 78785deb401a47fbbfdc58329eb2d6b9
parent_id: bc33dce65848438199af0fd3912185dd
created_time: 2025-06-24T10:41:15.908Z
updated_time: 2025-06-24T10:42:42.667Z
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
user_created_time: 2025-06-24T10:41:15.908Z
user_updated_time: 2025-06-24T10:42:42.667Z
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