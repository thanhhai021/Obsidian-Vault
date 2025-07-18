Khách hàng báo không nhận được email

## Khách hàng báo không nhận được email

1.  [](https://portal.hqv.biz/help)
2.  [Xử lý các lỗi](https://portal.hqv.biz/help/category/15)
3.  Khách hàng báo không nhận được email

**[![pasted_image_file68184db8c9edb-image_FklLA.png](:/4d5547cf2f3a4b2ca48deba9a68f90d9)](https://portal.hqv.biz/files/timeline_files/pasted_image_file68184db8c9edb-image_FklLA.png)**

**Vấn đề**

```
Không nhận được email từ địa chỉ xxx nào đó
```

**Các xử lý**

1.  **Tiếp nhận yêu cầu, báo khách hàng đợi để kiểm tra**
2.  Xác định có sử dụng antispamcloud.com hay không
3.  Nếu có antispamcloud.com, truy vấn theo điều kiện: From và To, trong đó, From là địa chỉ email cụ thể khách hàng cung cấp (nếu có), không thì truy vấn from là tên miền, To là tên miền nhận.
4.  Nếu không, kiểm tra trực tiếp server đích.

**Nếu thấy log với địa chỉ cụ thể**

```
Kiểm tra tiếp trên server đích
```

**Trả lời khách hàng**

1.  Nếu tất cả mọi thứ có, báo khách hàng thư nhận và có trên tài khoản của họ, khách hàng báo người dùng kiểm tra lại.
2.  Nếu không thấy địa chỉ cụ thể, chỉ thấy tên miền gửi đến, trả lời khách hàng

