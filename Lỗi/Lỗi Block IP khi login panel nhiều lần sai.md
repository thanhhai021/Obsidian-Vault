Bị block IP khi login panel nhiều lần sai

## **Bị block IP khi login panel nhiều lần sai**

**Nguyên nhân:**

- CSF, Fail2Ban, hoặc tính năng bảo vệ login.

**Cách xử lý:**

- Gỡ IP khỏi CSF:
    
    &nbsp;
    
    `csf -dr YOUR.IP.ADDRESScsf -tr YOUR.IP.ADDRESS`
    
- Thêm whitelist:
    
    &nbsp;
    
    `csf -a YOUR.IP.ADDRESS`

