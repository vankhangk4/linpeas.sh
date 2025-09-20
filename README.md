# LinPEAS (Privilege Escalation Awesome Script)

**LinPEAS** là một script bash được sử dụng để **enum thông tin hệ thống Linux** nhằm phát hiện các vector tiềm năng cho **Local Privilege Escalation (LPE)**.  
Đây là một phần của [PEAS project](https://github.com/carlospolop/PEASS-ng), trong đó còn có WinPEAS (Windows).

---

## 🚀 Tính năng chính
- Kiểm tra phiên bản kernel, packages và so khớp với **CVE** đã biết.  
- Liệt kê quyền sudo, SUID/SGID binaries.  
- Tìm kiếm file cấu hình/credential nhạy cảm.  
- Phát hiện service đang chạy với quyền cao.  
- Phân tích AppArmor, SELinux, seccomp và các bảo vệ kernel.  
- Tích hợp với Exploit Suggester để đưa ra CVE có thể khai thác.  

---

## 📥 Cài đặt
Clone project từ GitHub:
```bash
git clone https://github.com/carlospolop/PEASS-ng.git
cd PEASS-ng/linPEAS
```

---

## 🛠️ Cách sử dụng

Chạy trực tiếp script:
```bash
./linpeas.sh
```

Hoặc chạy nhanh từ remote:
```bash
curl -L https://github.com/carlospolop/PEASS-ng/releases/latest/download/linpeas.sh | sh
```

Chạy trong môi trường **noisy** (nhiều check hơn, có thể gây log):
```bash
./linpeas.sh -a
```

Lưu output ra file để phân tích:
```bash
./linpeas.sh > linpeas_report.txt
```

---

## 📊 Ví dụ kết quả

Một số thông tin nổi bật mà linpeas.sh có thể phát hiện:

- **Kernel exploits**:
  ```
  [+] [CVE-2021-4034] PwnKit
  [+] [CVE-2021-3560] Polkit LPE
  ```

- **SUID binaries**:
  ```
  /usr/bin/python3 (SUID bit set)
  /usr/bin/vim (SUID bit set)
  ```

- **Interesting files**:
  ```
  /etc/passwd
  /etc/shadow
  /var/backups/mysql.sql (world-readable)
  ```

---

## ⚠️ Lưu ý
- Chỉ sử dụng **linpeas.sh** trong môi trường lab, pentest hoặc CTF được phép.  
- Script có thể tạo nhiều log → cần thận trọng khi chạy trên hệ thống production.  

---

## 📚 Tham khảo
- GitHub: [https://github.com/carlospolop/PEASS-ng](https://github.com/carlospolop/PEASS-ng)  
- Cheatsheet privilege escalation: [GTFOBins](https://gtfobins.github.io/)  
