Script  autossl.sh

autossl.sh

#!/bin/bash  
USER="grandtop"  
DOMAIN_LIST=$(grep -h '^domain=' /usr/local/directadmin/data/users/$USER/domains/\*.conf | cut -d= -f2)

for DOMAIN in $DOMAIN_LIST; do  
  /usr/local/directadmin/scripts/letsencrypt.sh request "$DOMAIN" 4096 --email="admin@grandtopuni.com"  
done

\------

#!/bin/bash

\# Định nghĩa user và email bạn muốn sử dụng  
USER="newuser" # Đổi thành tên user mới  
EMAIL="email@newuser.com" # Đổi thành email của user mới

\# Lấy danh sách domain của user  
DOMAIN_LIST=$(grep -h '^domain=' /usr/local/directadmin/data/users/$USER/domains/\*.conf | cut -d= -f2)

\# Yêu cầu chứng chỉ SSL Let's Encrypt cho từng domain trong danh sách  
for DOMAIN in $DOMAIN_LIST; do  
  /usr/local/directadmin/scripts/letsencrypt.sh request "$DOMAIN" 4096 --email="$EMAIL"  
done

&nbsp;-----------------------------  
 #!/bin/bash

\# Định nghĩa danh sách người dùng và email  
declare -A USERS_EMAILS  
USERS_EMAILS=(  
  \["lavishto"\]="lavishto@lavishtopuni.com"  
  \["aristocr"\]="aristocr@aristocratictopuni.com"  
)

\# Định nghĩa danh sách các domain chính cần bỏ qua  
SKIP_DOMAINS=("lavishtopuni.com" "aristocratictopuni.com")

\# Tệp tin log chứa thông báo thành công về chứng chỉ  
LOG_FILE="/path/to/letsencrypt.log"

\# Lặp qua từng người dùng và email  
for USER in "${!USERS_EMAILS\[@\]}"; do  
  EMAIL="${USERS_EMAILS\[$USER\]}"

&nbsp; # Lấy danh sách domain của người dùng  
  DOMAIN_LIST=$(grep -h '^domain=' /usr/local/directadmin/data/users/$USER/domains/\*.conf | cut -d= -f2)

&nbsp; # Lặp qua từng domain trong danh sách  
  for DOMAIN in $DOMAIN_LIST; do  
    # Kiểm tra xem domain có nằm trong danh sách bỏ qua không  
    if \[\[ " ${SKIP_DOMAINS\[@\]} " =~ " ${DOMAIN} " \]\]; then  
      echo "Skipping domain: $DOMAIN for user: $USER"  
      continue # Bỏ qua domain này  
    fi

&nbsp;   # Kiểm tra xem domain đã được cấp chứng chỉ chưa dựa trên log  
    if grep -q "Certificate for $DOMAIN has been created successfully!" "$LOG_FILE"; then  
      echo "Domain $DOMAIN already issued, skipping."  
      continue # Bỏ qua nếu domain đã cấp chứng chỉ  
    fi

&nbsp;   # Nếu không bị bỏ qua và chưa cấp chứng chỉ, thực hiện yêu cầu chứng chỉ Let's Encrypt  
    /usr/local/directadmin/scripts/letsencrypt.sh request "$DOMAIN" 4096 --email="$EMAIL" >> "$LOG_FILE" 2>&1

&nbsp;   # Kiểm tra xem yêu cầu chứng chỉ có thành công hay không  
    if grep -q "Certificate for $DOMAIN has been created successfully!" "$LOG_FILE"; then  
      echo "Successfully issued certificate for domain: $DOMAIN"  
    else  
      echo "Failed to issue certificate for domain: $DOMAIN"  
    fi  
  done  
done

id: 8b47f7c7d87849e989a7d54f09c3aac0
parent_id: bc33dce65848438199af0fd3912185dd
created_time: 2025-04-15T07:14:44.727Z
updated_time: 2025-04-15T08:55:53.116Z
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
user_created_time: 2025-04-15T07:14:44.727Z
user_updated_time: 2025-04-15T08:55:53.116Z
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