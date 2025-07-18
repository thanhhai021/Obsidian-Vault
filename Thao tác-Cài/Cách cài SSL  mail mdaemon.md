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
