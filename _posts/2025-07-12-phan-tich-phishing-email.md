---
title: "[Phân tích] Phishing giả mạo Microsoft bằng Splunk"
date: 2025-07-12 20:00:00 +0700
categories: [SOC, Phishing]
tags: [Splunk, phishing, detection, DNS]
---

Trong bài lab này, mình mô phỏng một cuộc tấn công **phishing giả mạo Microsoft**, thu thập log DNS và phân tích bằng Splunk để phát hiện.

## 🧪 Mô phỏng tấn công
- Máy victim: Windows 10
- Máy attacker: Kali Linux
- Công cụ gửi email phishing: Gophish
- Domain giả mạo: `login-microsoft-support[.]com`

## 🔍 Thu thập DNS logs
- Splunk Forwarder thu thập DNS logs từ máy Windows
- Log chứa truy vấn đáng ngờ đến domain giả mạo

Ví dụ log:
