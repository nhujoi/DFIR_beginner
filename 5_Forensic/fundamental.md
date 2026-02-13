
## 1. Biểu diễn dữ liệu (Introduction to Data Representation)

Để phân tích dữ liệu ở mức thấp (low-level), điều tra viên cần hiểu ngôn ngữ của máy tính.

### Các đơn vị cơ bản
* **Bit (Binary Digit):** Đơn vị nhỏ nhất, chỉ có giá trị 0 hoặc 1.
* **Nibble:** Nhóm 4 bits (ví dụ: `1010`).
* **Byte:** Nhóm 8 bits. Đây là đơn vị lưu trữ cơ bản cho một ký tự văn bản.
* **Word:** Thường là 16, 32 hoặc 64 bits tùy kiến trúc máy tính.

### Hệ đếm (Number Systems)
* **Nhị phân (Binary - Base 2):** Chỉ dùng 0 và 1. Máy tính xử lý dữ liệu ở dạng này.
* **Thập phân (Decimal - Base 10):** Hệ đếm con người sử dụng (0-9).
* **Thập lục phân (Hexadecimal - Base 16):** Sử dụng 0-9 và A-F (A=10, B=11... F=15).
    * *Tại sao quan trọng:* Hex giúp biểu diễn chuỗi nhị phân dài một cách ngắn gọn, dễ đọc hơn cho con người (1 ký tự Hex = 4 bit nhị phân).

### Mã hóa ký tự (Character Encoding)
* **ASCII:** Tiêu chuẩn mã hóa ký tự cũ, dùng 7 bit để biểu diễn 128 ký tự (bảng chữ cái tiếng Anh).
* **Unicode:** Tiêu chuẩn hiện đại, bao gồm hầu hết các ký tự ngôn ngữ trên thế giới.

---

## 2. Phần cứng lưu trữ: HDD và SSD

Hiểu cách dữ liệu được lưu trữ vật lý là chìa khóa để phục hồi dữ liệu đã xóa.

### Ổ đĩa cứng (Hard Disk Drive Basics - HDD)
* **Cấu tạo:** Gồm các đĩa từ (platters) quay quanh trục và đầu đọc/ghi (heads) di chuyển trên bề mặt đĩa.
* **Cấu trúc dữ liệu:**
    * **Track:** Các vòng tròn đồng tâm trên mặt đĩa.
    * **Sector:** Đơn vị lưu trữ vật lý nhỏ nhất trên đĩa (thường là 512 bytes).
    * **Cluster:** Đơn vị cấp phát nhỏ nhất của hệ điều hành (gồm nhiều sector).
* **Không gian thừa (Slack Space):** Nơi chứa dữ liệu ẩn quan trọng.
    * **RAM Slack:** Phần không gian từ cuối dữ liệu thực đến hết sector hiện tại. Trước đây Windows điền dữ liệu ngẫu nhiên từ RAM vào đây (có thể chứa mật khẩu), nhưng các hệ điều hành mới thường điền số 0 (padded with zeros).
    * **Drive Slack:** Phần không gian từ cuối sector cuối cùng của tệp tin đến hết cluster. Dữ liệu cũ (deleted data) có thể vẫn còn tồn tại ở đây.

### Ổ đĩa thể rắn (SSD Drive Basics)
* **Công nghệ:** Sử dụng bộ nhớ Flash (NAND), không có bộ phận chuyển động. Nhanh hơn và bền hơn HDD.
* **Thách thức trong Điều tra số:**
    * **Lệnh TRIM:** Khi người dùng xóa file, hệ điều hành gửi lệnh TRIM báo cho SSD biết các block dữ liệu đó không còn cần thiết.
    * **Garbage Collection (Thu gom rác):** SSD sẽ chủ động xóa vĩnh viễn dữ liệu tại các block đã được đánh dấu TRIM để tối ưu hiệu suất ghi mới.
    * *Hậu quả:* Việc phục hồi dữ liệu đã xóa trên SSD khó khăn hơn nhiều so với HDD vì dữ liệu thực sự bị xóa đi thay vì chỉ bị đánh dấu là "đã xóa".

---

## 3. Hệ thống tập tin (File Systems)

Hệ thống tập tin quản lý cách dữ liệu được lưu trữ và truy xuất.

* **FAT (File Allocation Table):** Cũ hơn, đơn giản, độ tương thích cao (USB, thẻ nhớ) nhưng thiếu các tính năng bảo mật và khả năng phục hồi lỗi.
* **NTFS (New Technology File System):** Hệ thống mặc định của Windows hiện đại.
    * **MFT (Master File Table):** Cơ sở dữ liệu chứa thông tin về mọi tệp tin trên ổ đĩa (tên, kích thước, tem thời gian, quyền hạn).
    * **Journaling:** Ghi nhật ký các thay đổi trước khi thực hiện, giúp phục hồi dữ liệu khi mất điện đột ngột.
    * **Security:** Hỗ trợ phân quyền truy cập (ACLs) và mã hóa.

---

## 4. Xử lý bằng chứng số (Digital Evidence & Handling)

### Nguyên tắc cơ bản
* **Nguyên lý trao đổi Locard:** "Mọi sự tiếp xúc đều để lại dấu vết". Trong thế giới số, kẻ tấn công luôn để lại dấu vết (logs, registry, file fragments).
* **Bằng chứng số (Digital Evidence):** Bất kỳ thông tin nào có giá trị chứng minh được lưu trữ hoặc truyền tải dưới dạng kỹ thuật số.

### Quy trình xử lý
1.  **Chuỗi hành trình bằng chứng (Chain of Custody):** Tài liệu quan trọng nhất ghi lại lịch sử của bằng chứng: Ai thu thập? Khi nào? Ở đâu? Ai đã xử lý nó? Mục đích là để chứng minh tính toàn vẹn của bằng chứng trước tòa.
2.  **Túi Faraday (Faraday Bags):** Dùng để đựng thiết bị di động (điện thoại, máy tính bảng). Nó chặn sóng vô tuyến (Wifi, 4G, Bluetooth) để ngăn chặn việc xóa dữ liệu từ xa (remote wiping).

---

## 5. Thứ tự biến động (Order of Volatility)

Khi thu thập bằng chứng tại hiện trường, cần ưu tiên thu thập dữ liệu dễ mất trước. Theo chuẩn **RFC 3227**, thứ tự ưu tiên là:

1.  **Registers & Cache:** Bộ nhớ trong CPU (mất ngay lập tức khi tắt máy).
2.  **Routing Table, ARP Cache, Process Table, Kernel Statistics:** Thông tin trong RAM về trạng thái mạng và tiến trình đang chạy.
3.  **RAM (Random Access Memory):** Dữ liệu tạm thời (mất khi mất điện).
4.  **Temporary File Systems:** Các tệp tạm / Swap space.
5.  **Disk (Ổ cứng):** Dữ liệu lưu trữ lâu dài.
6.  **Remote Logging / Monitoring Data:** Dữ liệu lưu trên máy chủ khác.
7.  **Physical Configuration / Network Topology:** Cấu hình vật lý.
8.  **Archival Media:** Dữ liệu sao lưu (băng từ, đĩa CD/DVD).

---

## 6. Dữ liệu hệ thống & Bộ nhớ (Memory, Pagefile, Hibernation)

Nơi chứa các bằng chứng về hoạt động của người dùng và hệ thống.

* **RAM (Bộ nhớ khả biến):** Chứa các chương trình đang chạy, tài liệu đang mở, kết nối mạng, và có thể cả mật khẩu hoặc khóa giải mã chưa được mã hóa.
* **Pagefile.sys:** Bộ nhớ ảo trên ổ cứng. Khi RAM đầy, Windows chuyển dữ liệu ít dùng sang đây. Do đó, `pagefile.sys` có thể chứa các mảnh dữ liệu từ RAM mà điều tra viên cần.
* **Hiberfil.sys (File ngủ đông):** Khi máy tính chuyển sang chế độ ngủ đông (Hibernate), toàn bộ nội dung của RAM được sao chép vào tệp này trên ổ cứng. Đây là "mỏ vàng" cho điều tra viên vì nó là bản chụp nguyên vẹn của RAM tại thời điểm tắt máy.

---

## 7. Metadata và File Carving

### Metadata (Siêu dữ liệu)
* **Định nghĩa:** Dữ liệu về dữ liệu.
* **Ví dụ:** Trong một bức ảnh (EXIF data) có thể chứa: Kiểu máy ảnh, ngày giờ chụp, toạ độ GPS, cài đặt phơi sáng.
* **Ứng dụng:** Giúp xác định nguồn gốc tài liệu, thời gian tạo, và tác giả.

### File Carving (Khôi phục tập tin thô)
* **Khái niệm:** Kỹ thuật phục hồi tệp tin từ không gian đĩa (unallocated space) mà không cần dựa vào bảng hệ thống tập tin (như MFT hay FAT).
* **Cách hoạt động:** Dựa vào **File Signature** (Chữ ký tập tin) hay còn gọi là "Magic Numbers".
    * **Header:** Dãy hex đặc trưng đánh dấu sự bắt đầu của file (ví dụ: JPEG bắt đầu bằng `FF D8`).
    * **Footer:** Dãy hex đánh dấu sự kết thúc của file (ví dụ: JPEG kết thúc bằng `FF D9`).
* Công cụ sẽ quét ổ đĩa tìm Header và trích xuất dữ liệu cho đến khi gặp Footer tương ứng.

---

## 8. Băm và Tính toàn vẹn (Hashing and Integrity)

Làm sao để chứng minh bằng chứng không bị thay đổi trong quá trình điều tra?

* **Hash Function (Hàm băm):** Một thuật toán toán học một chiều chuyển đổi dữ liệu đầu vào (bất kể kích thước) thành một chuỗi ký tự có độ dài cố định (Digest/Fingerprint).
* **Tính chất:**
    * Cùng một đầu vào luôn cho ra cùng một mã băm.
    * Chỉ cần thay đổi 1 bit dữ liệu, mã băm sẽ thay đổi hoàn toàn (Hiệu ứng tuyết lở).
    * Không thể suy ngược lại dữ liệu gốc từ mã băm.
* **Các thuật toán phổ biến:**
    * **MD5:** 128-bit (Hiện nay được coi là yếu do nguy cơ đụng độ - collision).
    * **SHA-1:** 160-bit.
    * **SHA-256:** 256-bit (Được khuyến nghị sử dụng hiện nay).
* **Quy trình:**
    1.  Tính mã băm của ổ đĩa gốc tại hiện trường.
    2.  Tạo bản sao (Forensic Image).
    3.  Tính mã băm của bản sao.
    4.  Nếu 2 mã băm trùng khớp => Bằng chứng toàn vẹn (Integrity Verified).

https://gchq.github.io/CyberChef/
https://www.howtogeek.com/437958/how-to-use-the-chmod-command-on-linux/
https://www.computerhope.com/jargon/u/unicode.htm
