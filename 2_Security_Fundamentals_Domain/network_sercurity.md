# Hệ Thống Bảo Mật Mạng (Network Security Systems)

Sự kết hợp giữa các giải pháp phát hiện, ngăn chặn và kiểm soát giúp tạo ra một hệ thống phòng thủ đa lớp vững chắc cho tổ chức.

---

## 1. Hệ thống Phát hiện và Ngăn ngừa Xâm nhập (NIDS & NIPS)

Cả hai hệ thống đều giám sát lưu lượng mạng để tìm dấu hiệu tấn công, nhưng khác biệt lớn nhất nằm ở **phản ứng**.

### **NIDS (Network Intrusion Detection System)**
* **Chức năng:** Chỉ dùng để **phát hiện** và tạo cảnh báo. Các chuyên viên phân tích sẽ dựa vào cảnh báo này để điều tra.
* **Vị trí triển khai:**
    * **Network Tap:** Kết nối vật lý trực tiếp vào cáp mạng.
    * **Passive (SPAN port):** Kết nối vào một cổng trên thiết bị mạng (Switch) để nhận bản sao của lưu lượng (mirroring). 
    * *Ưu điểm:* Không làm gián đoạn luồng dữ liệu chính nếu hệ thống gặp sự cố.



### **NIPS (Network Intrusion Prevention System)**
* **Chức năng:** Có khả năng **tự động ngăn chặn** hành vi độc hại ngay khi phát hiện.
* **Vị trí triển khai:** * **Inline:** Nằm trực tiếp trên đường truyền dữ liệu.
    * *Cơ chế:* Có thể ngắt kết nối, chặn IP hoặc thiết lập lại (reset) các phiên làm việc độc hại.
* **Ví dụ:** Khi phát hiện một máy tính đang thực hiện hành vi quét mạng (scanning), NIPS sẽ tự động chặn toàn bộ liên lạc từ máy đó.

---

## 2. Tường lửa (Firewalls)

Tường lửa phân chia các vùng mạng và kiểm soát lưu lượng dựa trên bộ quy tắc bảo mật (Access Control Lists).

| Loại Tường Lửa | Đặc điểm & Chức năng |
| :--- | :--- |
| **Standard Firewalls** | Chạy trên phần cứng chuyên dụng, đặt tại các điểm cửa ngõ (Gateway) của mạng. |
| **Local Firewalls** | Phần mềm chạy trực tiếp trên thiết bị đầu cuối (ví dụ: Windows Firewall). |
| **Web Application Firewall (WAF)** | Chuyên biệt để bảo vệ máy chủ web khỏi các cuộc tấn công tầng ứng dụng (như SQL Injection, XSS). |

---

## 3. Giám sát Sự kiện (Event Monitoring & SIEM)

Tất cả nhật ký (logs) từ các thiết bị được tập trung về nền tảng **SIEM** để phân tích và tương quan dữ liệu.

* **Web Proxy Logs:** Ghi lại lịch sử truy cập web của người dùng. Giúp đối chiếu với danh sách đen (blacklist) để cảnh báo mã độc.
* **Perimeter Firewalls:** Theo dõi lưu lượng tại biên giới mạng để phát hiện sớm các cuộc tấn công **DDoS** hoặc **Port Scanning**.



---

## 4. Kiểm soát Truy cập Mạng (NAC - Network Access Control)

NAC đóng vai trò là "người gác cổng", đảm bảo thiết bị phải an toàn trước khi được phép vào mạng.

* **Cơ chế hoạt động:** Kiểm tra sự tuân thủ (Compliance) của thiết bị:
    * Đã cập nhật bản vá (Patch) mới nhất chưa?
    * Phần mềm diệt virus có đang hoạt động không?
* **Ứng dụng thực tế:**
    * **BYOD (Bring Your Own Device):** Quản lý thiết bị cá nhân của nhân viên.
    * **Captive Portals:** Các trang đăng nhập Wi-Fi tại sân bay/nhà hàng yêu cầu xác thực trước khi cấp quyền truy cập Internet.

---
> **Lưu ý:** Việc phối hợp giữa NIPS (ngăn chặn tức thời) và SIEM (phân tích dài hạn) giúp tổ chức có cái nhìn toàn diện về tình hình an ninh mạng.