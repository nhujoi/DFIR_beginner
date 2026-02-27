# Hướng Dẫn Chi Tiết Về Volatility (Pháp Y Bộ Nhớ)

## 1. Volatility là gì?
Volatility là một framework mã nguồn mở được sử dụng cho pháp y bộ nhớ (memory forensics), phản ứng sự cố (incident response) và phân tích mã độc (malware analysis). 
* Công cụ này được viết bằng ngôn ngữ Python và hỗ trợ các hệ điều hành Microsoft Windows, Mac OS X và Linux. 
* Volatility ban đầu được tạo ra bởi nhà khoa học máy tính Aaron Walters, dựa trên các nghiên cứu học thuật của ông về pháp y bộ nhớ.

**Các tính năng mạnh mẽ của Volatility bao gồm:**
* Liệt kê tất cả các tiến trình (processes) đang chạy.
* Liệt kê các kết nối mạng đang hoạt động và đã đóng.
* Xem lịch sử duyệt web (IE).
* Xác định các tệp trên hệ thống và trích xuất chúng từ bản sao bộ nhớ (memory dump).
* Đọc nội dung của các tài liệu notepad.
* Khôi phục các lệnh đã được nhập vào Windows Command Prompt (CMD).
* Quét sự hiện diện của phần mềm độc hại bằng các quy tắc YARA (YARA rules).
* Trích xuất ảnh chụp màn hình và nội dung trong khay nhớ tạm (clipboard).
* Trích xuất mật khẩu đã được băm (hashed passwords).
* Lấy các khóa và chứng chỉ SSL.

---

## 2. Khái Niệm Cơ Bản: Cấu hình (Profile)
Volatility cần các "profile" để hoạt động. Profile giúp Volatility nhận diện hệ thống mà bản sao bộ nhớ được lấy ra, bao gồm hệ điều hành, phiên bản và kiến trúc. Ví dụ: nếu bộ nhớ lấy từ máy Windows 7, Service Pack 1, kiến trúc 64-bit, cấu hình được đề xuất sẽ là `Win7SP1x64`.

**Cách xác định và sử dụng Profile:**
* Lệnh tìm profile: `volatility -f memdump.mem imageinfo`. Lệnh này sẽ cung cấp danh sách cấu hình đề xuất, địa chỉ KDBG, số lượng bộ xử lý và gói dịch vụ.
* Khi chạy bất kỳ lệnh nào khác, bạn bắt buộc phải cung cấp profile theo định dạng `--profile=TÊN_PROFILE` (ví dụ: `--profile=WinXPSP2x86`), nếu không lệnh sẽ không chạy.

---

## 3. Các Plugin Và Lệnh Quan Trọng

*Lưu ý: Tất cả các plugin đều phân biệt chữ hoa chữ thường!*

* **`pslist`**: In danh sách các tiến trình ra terminal. Lệnh này cho thấy các tiến trình đang chạy, bao gồm ID tiến trình và dấu thời gian.
  * *Lệnh*: `volatility -f memdump.mem --profile=PROFILE pslist`
* **`pstree`**: Giống như pslist nhưng hiển thị dưới dạng cây (tree format).
  * *Lệnh*: `volatility -f memdump.mem --profile=PROFILE pstree`
* **`psscan`**: In tất cả các tiến trình có sẵn, bao gồm cả các tiến trình ẩn thường được phần mềm độc hại sử dụng. 
  * *Lệnh*: `volatility -f memdump.mem --profile=PROFILE psscan`
* **`psxview`**: Là sự kết hợp của plugin pslist và psscan, dùng để in ra các tiến trình dự kiến và tiến trình bị ẩn.
  * *Lệnh*: `volatility -f memdump.mem --profile=PROFILE psxview`
* **`netscan`**: Xác định bất kỳ kết nối mạng nào đang hoạt động hoặc đã đóng từ thời điểm chụp bộ nhớ.
  * *Lệnh*: `volatility -f memdump.mem --profile=PROFILE netscan`
* **`timeliner`**: Tạo dòng thời gian của các sự kiện từ hình ảnh bộ nhớ. Rất hữu ích cho phản ứng sự cố để xây dựng dòng thời gian tuyến tính của các sự kiện.
  * *Lệnh*: `volatility -f memdump.mem --profile=PROFILE timeliner`
* **`iehistory`**: Trích xuất lịch sử duyệt web internet.
  * *Lệnh*: