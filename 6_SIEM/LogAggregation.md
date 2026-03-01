# Log Aggregation Explained

## 1. Định nghĩa Log Aggregation
Log aggregation là quá trình thu thập log từ nhiều hệ thống máy tính khác nhau, sau đó thực hiện các bước xử lý để biến dữ liệu thô thành thông tin có giá trị. Quá trình này bao gồm:
* **Thu thập (Collecting):** Gom log từ nhiều nguồn về một nơi.
* **Phân tích (Parsing):** Đọc và hiểu cấu trúc của log.
* **Trích xuất (Extracting):** Lấy ra các dữ liệu có cấu trúc.
* **Hợp nhất:** Đưa dữ liệu vào một định dạng chung giúp các công cụ hiện đại có thể dễ dàng tìm kiếm và khám phá.

---

## 2. Các phương pháp tổng hợp Log phổ biến
Có 4 phương pháp chính để thực hiện việc tổng hợp log, nhiều hệ thống SIEM thường kết hợp nhiều phương pháp này cùng lúc:

* **Syslog:** * Đây là một giao thức ghi nhật ký tiêu chuẩn. 
    * Quản trị viên thiết lập một máy chủ Syslog để nhận log từ nhiều hệ thống khác nhau.
    * Dữ liệu được lưu trữ dưới định dạng nén, hiệu quả và rất dễ dàng để truy vấn.

* **Event Streaming (Truyền phát sự kiện):**
    * Sử dụng các giao thức như SNMP, Netflow và IPFIX.
    * Các thiết bị mạng cung cấp thông tin tiêu chuẩn về hoạt động của chúng.
    * Bộ tổng hợp log sẽ chặn (intercept), phân tích cú pháp và thêm dữ liệu này vào bộ lưu trữ log trung tâm.

* **Log Collectors (Trình thu thập log):**
    * Sử dụng các phần mềm đại diện (agents) chạy trực tiếp trên các thiết bị mạng.
    * Các agent này có nhiệm vụ chụp lại thông tin log, phân tích cú pháp ngay tại chỗ và gửi về bộ tổng hợp trung tâm để phân tích sâu hơn.

* **Direct Access (Truy cập trực tiếp):**
    * Bộ tổng hợp log truy cập trực tiếp vào thiết bị hoặc hệ thống máy tính thông qua API hoặc các giao thức mạng.
    * Cách tiếp cận này đòi hỏi việc tích hợp tùy chỉnh (custom integration) cho từng nguồn dữ liệu cụ thể.

---

## 3. Phân loại dữ liệu trong SIEM
Khi đưa dữ liệu vào nền tảng SIEM, dữ liệu thường được chia làm hai loại:

### Dữ liệu có cấu trúc (Structured data)
* **Nguồn gốc:** Thường từ Apache, IIS, Windows events, log của Cisco và một số nhà sản xuất khác.
* **Đặc điểm:** Có các trường dữ liệu được định nghĩa cực kỳ rõ ràng (ví dụ: trường "src_ip").
* **Ưu điểm:** Rất dễ phân tích cú pháp và thực hiện chuẩn hóa (normalize).

### Dữ liệu không có cấu trúc (Unstructured data)
* **Nguồn gốc:** Thường đến từ các ứng dụng được xây dựng tùy chỉnh (custom-built).
* **Đặc điểm:** Mỗi thông báo có thể hiển thị khác nhau, một sự kiện có thể kéo dài nhiều dòng, không có điểm bắt đầu hoặc kết thúc sự kiện rõ ràng.
* **Lưu ý:** Đây thường là loại dữ liệu chiếm đa số trong các hệ thống SIEM.

---

## 4. Kỹ thuật Chuẩn hóa (Normalization)
Để thực hiện tìm kiếm hiệu quả trên một tập hợp lớn các loại log khác nhau, chúng ta cần sử dụng các kỹ thuật **chuẩn hóa**. Mục tiêu là đưa tất cả các log về cùng một định dạng chung, giúp việc truy vấn và phân tích trở nên nhất quán và dễ dàng hơn.