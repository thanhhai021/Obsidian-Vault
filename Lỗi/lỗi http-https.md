Fix lỗi http-https

### **Fix lỗi file `.htaccess` để chuyển hướng HTTP ➜ HTTPS**

apache

&nbsp;

`RewriteEngine On`

`RewriteCond %{HTTPS} off`

`RewriteRule ^ https://%{HTTP_HOST}%{REQUEST_URI} [L,R=301]`
