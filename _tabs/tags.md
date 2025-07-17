
---

# 🧪 Mô phỏng Phishing Website 

## 💡 Mục tiêu

Mô phỏng tấn công DNS spoofing kết hợp phishing để thu thập tài khoản người dùng trong môi trường nội bộ.

---

## 🛠️ Môi trường

| Thành phần | Hệ điều hành | Mục đích |
|------------|--------------|----------|
| **Attacker** | Kali Linux | Dựng web giả + DNS spoof |
| **Victim**   | Windows 10  | Truy cập và bị redirect |
| **Công cụ** | Apache2, PHP, Bettercap | |

---

## 🔨 Bước 1: Dựng Web Giả

Tạo file `index.html` và `login.php` để hiển thị form giả và ghi lại tài khoản + mật khẩu nhập vào.

### 🖼️ Cấu trúc thư mục `/var/www/html/`



```
├── index.html   -> form login
├── login.php    -> ghi lại thông tin user
└── creds.txt (sẽ được tạo sau khi user login)
```
### 🖼️ Tạo file index.html

<img src="../assets/src_index.png" width="512">

### 🖼️ Tạo file login.php

<img src="../assets/src_login.png" width="512">


## 🔨 Bước 2: Test form
🔧 1. Đảm bảo Apache đang chạy             ```  sudo service apache2 start```.

🌐 2. Truy cập form từ trình duyệt         ``` http://192.168.200.129``` 

🖱️ 3. Nhập thử tài khoản

<img src="../assets/src_loginweb.png" width="512">

📁 4. Kiểm tra file log         ```cat /var/www/html/creds.txt```

<img src="../assets/src_creds.png" width="512">

# KẾT QUẢ

Submit form không báo lỗi

Tự động redirect về ```https://accounts.google.com```

File ```creds.txt``` xuất hiện và chứa dòng như trên

# 🧪 Mô phỏng ARP Spoofing
## 💡 Mục tiêu
Khởi động ```bettercap```


<img src="../assets/src_bettercap.png" width="512">


 BƯỚC 2: Quét mạng tìm Victim

 <img src="../assets/src_scanbettercap.png" width="512">

 # ANALYSIC IP 
 
 <img src="../assets/src_analysic_IP.png" width="512">

