# CHI TIẾT VỀ AN NINH THIẾT BỊ ĐẦU CUỐI (ENDPOINT SECURITY)

Bài học này cung cấp nền tảng về các biện pháp bảo vệ thiết bị đầu cuối (máy tính cá nhân, laptop, máy chủ) khỏi các cuộc tấn công.

---

## 1. Hệ thống Phát hiện và Ngăn ngừa Xâm nhập Host (HIDS & HIPS)

Đây là các phần mềm được cài đặt trực tiếp trên thiết bị đầu cuối để theo dõi hoạt động nội bộ.

* **HIDS (Host Intrusion Detection System):**
    * Sử dụng các quy tắc để đối chiếu với hoạt động trên máy nhằm phát hiện các mẫu độc hại đã biết.
    * Nhiệm vụ chính là tạo ra cảnh báo (alerts) để các chuyên viên điều tra thông qua giao diện giải pháp hoặc đẩy về nền tảng SIEM.
* **HIPS (Host Intrusion Prevention System):**
    * Hoạt động tương tự HIDS nhưng có khả năng tự hành động để bảo vệ hệ thống ngay khi phát hiện xâm nhập.
    * Các hành động có thể bao gồm: ngắt kết nối với website/địa chỉ IP, xóa tệp độc hại hoặc tạo cảnh báo.

## 2. Giải pháp Diệt Virus (Anti-Virus - AV)

AV là lớp bảo mật cơ bản nên được triển khai trên mọi thiết bị đầu cuối để phát hiện và loại bỏ mã độc.

| Loại AV | Cách thức hoạt động | Hạn chế/Đặc điểm |
| :--- | :--- | :--- |
| **Dựa trên chữ ký (Signature-based)** | Sử dụng các mẫu đặc trưng (signatures) của mã độc đã được ghi nhận trước đó. | Không thể phát hiện mã độc mới nếu nhà cung cấp chưa có chữ ký trong cơ sở dữ liệu. |
| **Dựa trên hành vi (Behavior-based)** | Thiết lập một "ngưỡng chuẩn" cho hoạt động bình thường và xác định các sai lệch hoặc bất thường. | Có khả năng phát hiện các hành vi không theo quy ước hoặc mã độc chưa từng thấy. |

## 3. Phản ứng và Phát hiện Thiết bị đầu cuối (EDR)

**EDR (Endpoint Detection & Response)** là các tác nhân (agents) chạy ngầm trên thiết bị, cung cấp khả năng giám sát và phản ứng mạnh mẽ.

* **Điều tra chuyên sâu:** Cho phép chuyên viên xem trực tiếp các tiến trình (processes) đang chạy và phân tích chi tiết hoạt động đáng ngờ ngay trên nền tảng.
* **Mối đe dọa nội bộ:** Theo dõi hành vi người dùng (trang web đã truy cập, tin nhắn đã gửi, chương trình đã chạy) để phát hiện insider threats.

## 4. Quét lỗ hổng (Vulnerability Scanning)

Quá trình này giúp phát hiện lỗi cấu hình và các điểm yếu bảo mật có thể bị khai thác.

* **Quét từ bên ngoài (External):** Cung cấp "góc nhìn của kẻ tấn công" đối với các hệ thống công khai (internet-facing).
* **Quét từ bên trong (Internal):** Cung cấp cái nhìn toàn diện hơn về tình trạng bảo mật của mạng nội bộ.
* **Phân loại theo quyền truy cập:**
    * **Credentialed (Có thông tin đăng nhập):** Scanner có quyền cao để thu thập thông tin chi tiết về phiên bản phần mềm và cấu hình.
    * **Non-credentialed (Không có thông tin đăng nhập):** Phản ánh thực tế những gì kẻ tấn công thấy, giúp ưu tiên xử lý các lỗ hổng dễ bị khai thác.

## 5. Giám sát sự kiện và Tuân thủ

* **Giám sát sự kiện:** Sử dụng Syslog để gửi nhật ký từ thiết bị đầu cuối về nền tảng SIEM để tổng hợp và phân tích.
* **Quét tuân thủ (Compliance Scanning):** Sử dụng các cấu hình sẵn có để kiểm tra xem hệ thống có đáp ứng các tiêu chuẩn bảo mật tối thiểu của các khung quy định hay không.

---
