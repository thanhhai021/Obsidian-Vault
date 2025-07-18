Fix lỗi không remote navicat từ xa được

lỗi không remote navicat từ xa được  
mysql -u root -p  
vào vps chạy lệnh grant:  
GRANT ALL PRIVILEGES ON database_name.\* TO 'username'@'remote_host' IDENTIFIED BY 'password';
