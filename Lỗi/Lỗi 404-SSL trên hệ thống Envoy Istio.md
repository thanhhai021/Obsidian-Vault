Lỗi 404-SSL trên hệ thống Envoy/Istio

# Quy trình kiểm tra và khắc phục lỗi 404 làm đóng SSL trên hệ thống Envoy/Istio

* * *

## 1\. Kiểm tra hệ thống có sử dụng Envoy/Istio hay không

### 1.1. Kiểm tra HTTP Response Headers

bash

Copy code

`curl -I https://your-website.com`

- Nếu thấy header:

text

Copy code

`server: istio-envoyx-envoy-upstream-service-time: <time>x-request-id: <id>`

→ Hệ thống đang dùng Envoy (và khả năng cao là Istio).

* * *

### 1.2. Kiểm tra port liên quan đến Envoy

bash

Copy code

`ss -tuln | grep 1500`

- Nếu thấy port `15001`, `15006` đang listen → Envoy Sidecar đang chạy.

* * *

### 1.3. Kiểm tra tiến trình Envoy (nếu SSH được vào host)

bash

Copy code

`ps aux | grep envoy`

- Nếu có tiến trình `envoy`, xác nhận Envoy Proxy đang hoạt động.

* * *

### 1.4. Kiểm tra Pod và Service trong Kubernetes (nếu có quyền)

bash

Copy code

`kubectl get pods --all-namespaces -o wide | grep istiokubectl get svc --all-namespaces | grep istio`

- Nếu thấy các pod/service như `istio-ingressgateway`, `istiod`, hoặc container `istio-proxy` → Đang dùng Istio + Envoy.

* * *

## 2\. Nguyên nhân lỗi SSL khi 404

- Khi Envoy nhận request lỗi 404, nếu **không trả lại HTTP response** đầy đủ mà **đóng kết nối thô**, client sẽ báo lỗi SSL.
    
- Cần cấu hình Envoy/Istio để trả về HTTP 404 với **body HTML** và **header Content-Type: text/html** đúng chuẩn.
    

* * *

## 3\. Cách khắc phục lỗi

### 3.1. Nếu quản lý trực tiếp Envoy (không qua Istio)

**Sửa file cấu hình Envoy** (hoặc patch config Envoy) để thêm phần `local_reply_config` như sau:

yaml

Copy code

`local_reply_config: mappers: - filter: status_code_filter: comparison: op: EQ value: default_value: 404 body: inline_string: "<html><body><h1>404 Not Found</h1></body></html>" headers_to_add: - header: key: content-type value: text/html`

✅ Cấu hình này sẽ:

- Khi gặp lỗi 404, Envoy trả về body HTML nhỏ.
    
- Gửi thêm header `Content-Type: text/html`.
    

Sau khi sửa xong, restart Envoy để áp dụng.

* * *

### 3.2. Nếu hệ thống dùng Istio (Kubernetes Gateway, VirtualService)

**Tạo một `EnvoyFilter` để can thiệp lỗi 404**.

Ví dụ file `envoyfilter-404.yaml`:

yaml

Copy code

`apiVersion: networking.istio.io/v1alpha3kind: EnvoyFiltermetadata: name: custom-404-reply namespace: your-namespacespec: workloadSelector: labels: app: your-app-label configPatches: - applyTo: NETWORK_FILTER match: listener: filterChain: filter: name: "envoy.filters.network.http_connection_manager" patch: operation: MERGE value: typed_config: "@type": type.googleapis.com/envoy.extensions.filters.network.http_connection_manager.v3.HttpConnectionManager local_reply_config: mappers: - filter: status_code_filter: comparison: op: EQ value: default_value: 404 body: inline_string: "<html><body><h1>404 Page Not Found</h1></body></html>" headers_to_add: - header: key: "content-type" value: "text/html"`

Sau đó apply EnvoyFilter:

bash

Copy code

`kubectl apply -f envoyfilter-404.yaml`

✅ Cấu hình này sẽ:

- Khi lỗi 404, Istio/Envoy tự trả lại HTML thay vì reset connection.

* * *

## 4\. Kiểm tra lại sau khi sửa

Sau khi cấu hình, cần kiểm tra lại:

bash

Copy code

`curl -I https://your-website.com/duong-dan-sai`

Kết quả mong muốn:

text

Copy code

`HTTP/1.1 404 Not Foundcontent-type: text/htmlserver: istio-envoy...`

- Phải có `content-type: text/html`
    
- Không còn lỗi SSL
    
- Body trả về là trang 404 hợp lệ.
    

* * *

# 📚 Tổng kết nhanh

| Bước | Nội dung |
| --- | --- |
| 1   | Kiểm tra hệ thống có dùng Envoy/Istio hay không |
| 2   | Hiểu nguyên nhân SSL lỗi khi đóng kết nối sai |
| 3   | Cấu hình Envoy hoặc EnvoyFilter để trả về body HTML khi 404 |
| 4   | Kiểm tra lại hệ thống sau khi sửa |

id: 9926e8c2db6746acbdfc6581cbc10f11
parent_id: bc33dce65848438199af0fd3912185dd
created_time: 2025-04-29T02:20:12.630Z
updated_time: 2025-06-16T06:07:15.901Z
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
user_created_time: 2025-04-29T02:20:12.630Z
user_updated_time: 2025-06-16T06:07:15.901Z
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