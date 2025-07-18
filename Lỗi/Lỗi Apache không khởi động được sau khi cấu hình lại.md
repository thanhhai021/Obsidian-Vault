Apache không khởi động được sau khi cấu hình lại

## **Apache không khởi động được sau khi cấu hình lại**

**Nguyên nhân:**

- Cấu hình sai trong file `httpd.conf` hoặc `.htaccess`.
    
- Thiếu module cần thiết.
    

**Cách xử lý:**

- Kiểm tra cấu hình Apache:
    
    &nbsp;
    
    `apachectl configtest`
    
- Nếu có lỗi, Apache sẽ chỉ ra vị trí và loại lỗi.
    
- Đảm bảo các module cần thiết đã được bật, ví dụ:
    
    &nbsp;
    
    &nbsp;
    
    `a2enmod rewrite`
    
- Restart Apache:
    
    &nbsp;
    
    `systemctl restart apache2`

