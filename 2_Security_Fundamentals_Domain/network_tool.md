# TỔNG HỢP KIẾN THỨC BẢO MẬT & CÔNG CỤ MẠNG (BLUE TEAM)

Tài liệu này tổng hợp các khái niệm cốt lõi về phòng thủ mạng, bảo mật email, giao thức mạng và các công cụ dòng lệnh thiết yếu cho việc phân tích và phản ứng sự cố.

---

## 1. Hệ Thống Phòng Thủ Mạng (Network Security Systems)

### **Hệ thống Phát hiện & Ngăn ngừa Xâm nhập (IDS/IPS)**
* **NIDS (Network Intrusion Detection System):**
    * **Chức năng:** Chỉ phát hiện và tạo cảnh báo cho chuyên viên phân tích.
    * **Triển khai:** Dạng **Passive** (thụ động) thông qua *Network Tap* hoặc cổng *SPAN (Mirroring)* để nhận bản sao lưu lượng mà không ảnh hưởng đến luồng dữ liệu chính.
* **NIPS (Network Intrusion Prevention System):**
    * **Chức năng:** Có khả năng tự động ngăn chặn hành vi độc hại ngay khi phát hiện.
    * **Triển khai:** Dạng **Inline** (nằm trực tiếp trên đường truyền) để có thể chặn IP, ngắt kết nối hoặc reset phiên làm việc.

### **Tường lửa (Firewalls)**
* **Standard Firewalls:** Phần cứng chuyên dụng đặt tại biên giới mạng.
* **Local Firewalls:** Phần mềm chạy trên máy trạm (ví dụ: Windows Firewall).
* **WAF (Web Application Firewall):** Bảo vệ ứng dụng web khỏi các tấn công lớp ứng dụng (như SQL Injection, XSS).

### **Giám sát & Kiểm soát (SIEM & NAC)**
* **SIEM (Security Information and Event Management):** Thu thập nhật ký (logs) từ tường lửa, proxy, server về một nơi tập trung để phân tích tương quan và phát hiện sớm dấu hiệu tấn công (như quét cổng, DDoS).
* **NAC (Network Access Control):** Đảm bảo thiết bị phải tuân thủ chính sách (đã update patch, có antivirus) mới được kết nối vào mạng. Áp dụng cho BYOD và mạng khách (Captive Portals).

---

## 2. An Ninh Email (Email Security)

Email là vector tấn công số 1, nhắm vào con người thay vì lỗi kỹ thuật.

* **Spam Filter:** Lớp đầu tiên giúp lọc thư rác và email độc hại cơ bản.
* **Email Scanning:** Quét sâu vào tiêu đề (header) và nội dung (body) để tìm URL/file đính kèm độc hại. Email nghi ngờ sẽ bị **cách ly (quarantine)**.
* **DLP (Data Loss Prevention):** Ngăn chặn dữ liệu nhạy cảm (thông tin ngân hàng, PII) bị gửi ra ngoài. Sử dụng từ khóa hoặc Regex để kiểm soát nội dung email đi.
* **Security Awareness Training:** Đào tạo nhân viên nhận biết Phishing và thực hiện các chiến dịch giả lập tấn công để đo lường mức độ cảnh giác.

---

## 3. Cơ Sở Mạng (Network Fundamentals)

### **Giao thức Truyền tải (Transport Protocols)**
* **TCP (Transmission Control Protocol):**
    * Giao thức hướng kết nối, tin cậy (đảm bảo toàn vẹn dữ liệu).
    * **Bắt tay 3 bước:**
        1.  **SYN:** Khách gửi yêu cầu kết nối.
        2.  **SYN-ACK:** Chủ xác nhận và gửi lại thông số.
        3.  **ACK:** Khách xác nhận lần cuối -> Kết nối thiết lập (Established).
* **UDP (User Datagram Protocol):**
    * Giao thức không kết nối, tốc độ cao nhưng không tin cậy (không kiểm tra lỗi, không đảm bảo thứ tự). Dùng cho streaming, VoIP.

### **Giao thức & Địa chỉ khác**
* **ICMP:** Dùng để chẩn đoán mạng (ví dụ: lệnh `ping`).
* **IP Address:** Định danh logic của thiết bị.
    * *Private IP:* Dùng trong mạng LAN (192.168.x.x, 10.x.x.x).
    * *Public IP:* Dùng trên Internet.
* **MAC Address:** Định danh vật lý (phần cứng) của card mạng. Có thể bị giả mạo (spoofing).

---

## 4. Công Cụ Mạng (Network Tools)

Các công cụ dòng lệnh (Command-line) giúp xử lý sự cố và điều tra bảo mật.

### **Kiểm tra cấu hình & Kết nối**
* **`ip` (Linux) / `ipconfig` (Windows):** Xem IP, Gateway, DNS, trạng thái card mạng.
    * `ip a`: Xem tất cả địa chỉ IP.
* **`traceroute` (Linux) / `tracert` (Windows):** Theo dõi đường đi của gói tin qua các trạm (hops) để tìm điểm nghẽn mạng.
* **`dig` / `nslookup`:** Truy vấn DNS.
    * `dig [domain] MX`: Tìm mail server.
    * `dig [domain] ANY`: Lấy toàn bộ bản ghi DNS.

### **Giám sát & Quét mạng**
* **`netstat`:** Xem các kết nối TCP/UDP đang hoạt động trên máy. Giúp phát hiện malware kết nối ra C2 server.
    * `netstat -a -b`: Xem kết nối kèm tên chương trình thực thi.
* **`nmap` (Network Mapper):** Công cụ quét mạng mạnh mẽ nhất.
    * **Các lệnh phổ biến:**
        * `-v`: Tăng độ chi tiết (Verbose).
        * `-O`: Nhận diện hệ điều hành.
        * `-F`: Quét nhanh (Fast scan).
        * `-sS`: **TCP SYN Scan (Half Scan)** - Quét âm thầm, không hoàn thành bắt tay 3 bước.
        * `-sT`: **TCP Connect Scan** - Quét đầy đủ, dễ bị phát hiện hơn.
        * `-sV`: Phát hiện phiên bản dịch vụ đang chạy.

---

### **Tài liệu tham khảo & Download**

* **Tải Nmap:** [https://nmap.org/download.html](https://nmap.org/download.html)
* **SANS Nmap Cheat Sheet:** [https://www.sans.org/blog/sans-pen-test-cheat-sheet-nmap-v1-1/](https://www.sans.org/blog/sans-pen-test-cheat-sheet-nmap-v1-1/)
* **StationX Nmap Cheat Sheet:** [https://s3-us-west-2.amazonaws.com/stationx-public-download/nmap_cheet_sheet_0.6.pdf](https://s3-us-west-2.amazonaws.com/stationx-public-download/nmap_cheet_sheet_0.6.pdf)
* **Tài liệu Nmap Scripting Engine (NSE):** [https://nmap.org/book/nse.html](https://nmap.org/book/nse.html)