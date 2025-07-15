---
title: "DNS Spoofing & Phishing Lab"
layout: default
permalink: /labs/
---

# 🧪 DNS Spoofing & Phishing Lab

## 🎯 Mục tiêu
Mô phỏng tấn công DNS spoofing kết hợp phishing để thu thập tài khoản người dùng trong môi trường nội bộ.

## 🧱 Môi trường
| Thành phần | Hệ điều hành              |         Mục đích         |
|------------|-------------- ------------|--------------------------|
| Attacker   | Kali Linux                | Dựng web giả + DNS spoof |
| Victim     | Windows 10                | Truy cập và bị redirect  |
| Công cụ    | Apache2, PHP, Bettercap   |                          |

## 🔨 Bước 1: Dựng Web Giả

Tạo `index.html` và `login.php` để hiển thị form và ghi lại tài khoản + mật khẩu.

📸 Ảnh: Cấu trúc thư mục `/var/www/html`  
<img width="512" height="210" alt="image" src="https://github.com/user-attachments/assets/535e4669-1437-485a-8198-35f63bd46970" />

📸 Ảnh: Giao diện web login

## 📄 Bước 2: Ghi Log

Khi người dùng điền form, dữ liệu được ghi vào `creds.txt`

📸 Ảnh: Nội dung file `creds.txt` sau khi victim login

## 🌐 Bước 3: DNS Spoofing

Dùng Bettercap để redirect truy cập từ `accounts.google.com` về máy Kali.

```bash
set dns.spoof.domains accounts.google.com
set dns.spoof.address 192.168.1.100
dns.spoof on
