# TỔNG QUAN VỀ ĐIỀU TRA SỐ (DIGITAL FORENSICS) - BLUE TEAM LEVEL 1

## 1. Giới thiệu về Digital Forensics (Điều tra số)
**Digital Forensics** là quá trình thu thập, phân tích và bảo quản các bằng chứng kỹ thuật số, thường nhằm mục đích sử dụng trước tòa án trong các thủ tục pháp lý.

* **Sự khác biệt giữa Computer Forensics và DFIR:**
    * *Computer Forensics:* Thường gợi lên hình ảnh cảnh sát tịch thu thiết bị máy tính. Đây là cốt lõi của điều tra số.
    * *DFIR (Digital Forensics and Incident Response):* Khi điều tra số được kết hợp với ứng cứu sự cố bởi các đội an ninh mạng (security teams), thuật ngữ DFIR thường được sử dụng.

---

## 2. Quy trình Điều tra số (The Digital Forensics Process)
Đây là quy trình khoa học và pháp y được công nhận, chủ yếu dùng trong điều tra máy tính và thiết bị di động. Dữ liệu kỹ thuật số bị thu giữ thường được gọi là "vật chứng" (exhibit) trong thuật ngữ pháp lý.

Quy trình bao gồm 5 giai đoạn cơ bản:

1.  **Identification (Nhận diện):** Xác định các nguồn bằng chứng hoặc thông tin tiềm năng (thiết bị), cũng như những người quản lý dữ liệu (custodians) và vị trí của dữ liệu.
2.  **Preservation (Bảo quản):** Quá trình bảo vệ thông tin lưu trữ điện tử (ESI) liên quan. Việc này bao gồm bảo vệ hiện trường sự cố, chụp ảnh hiện trường và ghi lại mọi thông tin liên quan đến bằng chứng và cách nó được thu thập.
3.  **Collection (Thu thập):** Thu thập thông tin kỹ thuật số có thể liên quan đến cuộc điều tra. Bước này có thể bao gồm việc di dời thiết bị điện tử khỏi hiện trường và sau đó tạo ảnh (imaging), sao chép hoặc in nội dung của chúng.
4.  **Analysis (Phân tích):** Tìm kiếm hệ thống chuyên sâu các bằng chứng liên quan đến sự cố. Kết quả đầu ra là các đối tượng dữ liệu (như tệp tin hệ thống và tệp do người dùng tạo). Mục đích là đưa ra kết luận dựa trên bằng chứng tìm thấy.
5.  **Reporting (Báo cáo):** Các báo cáo dựa trên kỹ thuật và phương pháp đã được chứng minh để các giám định viên khác có thể tái hiện lại kết quả tương tự.

### Các hoạt động quan trọng đi kèm:
* **Ghi chép đồng thời (Contemporaneous note-taking):** Ghi lại tài liệu về những gì bạn đã làm *ngay sau khi* hoàn thành. Ghi chú phải đủ chi tiết để người khác có thể tái hiện lại quá trình chỉ dựa trên ghi chú đó.
* **Chain of Custody (Chuỗi hành trình bằng chứng):** Phải được tuân thủ ở mọi giai đoạn điều tra để đảm bảo tính toàn vẹn của bằng chứng không bị xâm phạm.

---

## 3. Thuật ngữ & Công cụ quan trọng (Glossary)

### Các khái niệm cơ bản
* **IOC (Indicator of Compromise):** Thông tin tình báo thu thập được từ hoạt động độc hại hoặc sự cố (ví dụ: mã băm của malware, tên file độc hại).
* **TTP (Tools, Techniques, and Procedures):** Hơn 240 chiến thuật độc đáo được MITRE định nghĩa mà kẻ thù sử dụng.
* **PCAP (Packet Capture):** Tệp chứa thông tin lưu lượng mạng đã được ghi lại bởi các công cụ như Wireshark.
* **ACPO (Association of Chief Police Officers):** Cung cấp bộ nguyên tắc hướng dẫn cho bằng chứng dựa trên máy tính để đảm bảo tính hợp lệ trước tòa.

### Phần cứng
* **HDD (Hard Disk Drive):** Ổ đĩa cứng sử dụng đĩa từ quay.
* **SSD (Solid State Disk Drive):** Ổ đĩa thể rắn sử dụng bộ nhớ flash, không có đĩa quay.
* **Write-Blocker:** Thiết bị phần cứng hoặc phần mềm ngăn chặn việc ghi dữ liệu lên ổ đĩa, đảm bảo bằng chứng không bị thay đổi.

### Công cụ phần mềm
* **KAPE (Kroll Artifact Parser and Extractor):** Công cụ giúp thu thập nhanh các bằng chứng kỹ thuật số quan trọng trong vài phút thay vì mất hàng giờ để sao chép toàn bộ.
* **FTK Imager:** Công cụ miễn phí cho phép tạo ảnh ổ đĩa (disk images) theo từng bit và gắn (mount) ảnh đĩa ở chế độ chỉ đọc.
* **BHC (Browser History Capturer):** Công cụ thu thập các tệp cốt lõi từ trình duyệt web.
* **BHV (Browser History Viewer):** Công cụ phân tích lịch sử duyệt web, hình ảnh cache.

### Tệp tin hệ thống Linux
* **`/etc/passwd`:** Chứa thông tin về tất cả tài khoản người dùng trên hệ thống Linux.
* **`/etc/shadow`:** Chứa mật khẩu đã được mã hóa của các tài khoản.

---

## 4. Tài liệu đọc thêm 

* **Digital Forensics Resources by Forensic Focus**
    https://www.forensicfocus.com/articles/digital-forensics-resources/

* **Digital Forensics Cheat sheet by Tech Republic**
    https://www.techrepublic.com/article/digital-forensics-the-smart-persons-guide/

* **A Guide to Digital Forensics and Cybersecurity Tools (2020) by Forensics Colleges**
    https://www.forensicscolleges.com/blog/resources/guide-digital-forensics-tools
