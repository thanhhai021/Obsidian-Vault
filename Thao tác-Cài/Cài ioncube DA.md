Build ioncube DA

build ioncube

&nbsp; 34 cd /usr/local/directadmin/custombuild  
   35 ./build set ioncube yes  
   36 ./build ioncube  
   37 php -v  
   38 cd /usr/local/directadmin/custombuild  
   39 ./build set ioncube yes  
   40 ./build ioncube  
   41 cd /usr/local/directadmin/custombuild  
   42 ./build set php1_release 7.4  
   43 ./build php n  
   44 ./build set ioncube yes  
   45 ./build ioncube  
   46 free -n  
   47 free -m  
   48 topc  
   49 htop  
   50 cd /usr/local/directadmin/custombuild  
   51 vi options.conf  
   52 ./build update  
   53 ./build php n  
   54 ./build rewrite_confs  
   55 curl -Lso- tocdo.net/share | bash  
   56 cd /usr/local/directadmin/custombuild  
   57 ./build set ioncube yes  
   58 ./build ioncube  
   59 cd /usr/local/directadmin/custombuild/  
   60 nano options.conf  
   61 ./build ioncube  
   62 ./build rewrite_confs  
   63 nano options.conf  
   64 ./build ioncube_loader  
   65 history  
   66 cd /usr/local/directadmin/custombuild  
   67 nano options.conf  
   68 ./build update  
   69 ./build set ioncube yes  
   70 ./build ioncube  
   71 wget https://downloads.ioncube.com/loader_downloads/ioncube_loaders_lin_x86-64.tar.gz  
   72 tar xvfz ioncube_loaders_lin_x86-64.tar.gz  
   73 wget https://downloads.ioncube.com/loader_downloads/ioncube_loaders_lin_x86-64.tar.gz  
   74 tar -zxvf ioncube_loaders_lin_x86-64.tar.gz  
   75 cp ioncube/ioncube_loader_lin_8.1.so /usr/local/lib/php/extensions/no-debug-non-zts-20190902/  
   76 cp ioncube/ioncube_loader_lin_8.1.so /usr/local/lib/ioncube/  
   77 cp ioncube/ioncube_loader_lin_8.1.so /usr/local/php81/lib/php/extensions/no-debug-non-zts-20210902/  
   78 service php-fpm81 restart  
   79 reboot
