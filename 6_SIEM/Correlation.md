# Normalization và Processing trong SIEM

Trong hệ thống SIEM (Security Information and Event Management), việc xử lý và chuẩn hóa dữ liệu là các bước then chốt để giúp các nhà phân tích bảo mật có thể truy vấn và phân tích dữ liệu từ nhiều nguồn khác nhau một cách hiệu quả.

---

## 1. Normalization (Chuẩn hóa)

### Định nghĩa
Normalization là quá trình chuyển đổi các định dạng log khác nhau từ nhiều thiết bị (phần mềm, phần cứng) thành một định dạng chung duy nhất. Vì hiện nay không có một tiêu chuẩn định dạng log toàn cầu, mỗi thiết bị sẽ ghi lại dữ liệu theo cách riêng của nó.

### Mục đích
- Giúp SIEM hiểu và phân loại được các thuộc tính của log.
- Cho phép các nhà phân tích thực hiện tìm kiếm nhất quán trên toàn bộ dữ liệu được lưu trữ.
- Giảm tải cho hệ thống khi thực hiện truy vấn.

### Ví dụ thực tế
- Thiết bị **Cisco** lưu địa chỉ IP nguồn dưới tên trường là `src_ip`.
- Thiết bị **Juniper** lưu địa chỉ IP nguồn dưới tên trường là `source_address`.
- **Sau khi Normalization:** Cả hai trường trên sẽ được gộp chung vào một thuộc tính duy nhất là `source_ip`. Khi đó, nhà phân tích chỉ cần tìm kiếm theo `source_ip` để xem kết quả từ cả hai loại thiết bị.

---

## 2. Categorization (Phân loại)

Categorization là việc gán thêm ý nghĩa cho các sự kiện. Quá trình này giúp xác định dữ liệu log đó liên quan đến loại hoạt động nào, chẳng hạn như:
- Sự kiện hệ thống (System events).
- Quá trình xác thực (Authentication).
- Các hoạt động nội bộ hoặc từ xa (Local/Remote operations).

---

## 3. Log Enrichment (Làm giàu dữ liệu)

Làm giàu dữ liệu là quá trình thêm các thông tin quan trọng vào log để giúp dữ liệu trở nên hữu ích hơn cho việc điều tra.

- **Ví dụ:** Một bản ghi log gốc chỉ chứa địa chỉ IP công cộng (Public IP). Quá trình Enrichment sẽ thực hiện một lệnh tra cứu (lookup) để xác định vị trí địa lý (Geographical location) của IP đó.
- **Lợi ích:** Cung cấp ngay lập tức thông tin về quốc gia của IP, giúp hỗ trợ điều tra và xây dựng các biểu đồ số liệu (metrics) chính xác hơn.

---

## 4. Log Indexing (Đánh chỉ mục)

SIEM thường phải xử lý một lượng dữ liệu khổng lồ. Việc tìm kiếm xuyên suốt dữ liệu trong nhiều tuần có thể rất chậm nếu không có Indexing.

- **Cơ chế:** Đánh chỉ mục các thuộc tính chung của một lượng lớn log.
- **Lợi ích:** Thay vì phải quét qua từng mẩu dữ liệu trong kho lưu trữ (scan every single piece), SIEM có thể tìm thấy kết quả nhanh hơn nhiều dựa trên các chỉ mục đã tạo.

---

## 5. Log Storage (Lưu trữ Log)

Việc quản lý lưu trữ cho SIEM là một thách thức lớn đối với các tổ chức quy mô lớn.

- **Các lựa chọn lưu trữ:**
    - Máy chủ tại chỗ (On-premises servers).
    - Các giải pháp đám mây như Amazon Web Services (AWS) S3 buckets.
    - Hệ thống lưu trữ phân tán như Hadoop.
- **Yếu tố cân nhắc:** Khi chọn giải pháp lưu trữ, các đội ngũ bảo mật cần cân nhắc về **Chi phí**, **Tính dễ sử dụng** và **Khả năng mở rộng (Scalability)**.

---

## 6. Các thành phần liên quan khác trong SIEM
- **Correlation (Tương quan):** Liên kết các sự kiện rời rạc để phát hiện chuỗi tấn công.
- **SIEM Rules:** Các quy tắc phát hiện dựa trên điều kiện có sẵn.
- **Sigma Rules:** Định dạng quy tắc chung có thể sử dụng trên nhiều nền tảng SIEM.
- **Regex (Regular Expression):** Sử dụng biểu thức chính quy để trích xuất hoặc khớp dữ liệu trong log.


# Tìm hiểu về SIEM Rules (Quy tắc SIEM)

SIEM Rules (các quy tắc trong hệ thống Quản lý Sự kiện và Thông tin Bảo mật) đóng vai trò là "bộ não" giúp các chuyên gia bảo mật phát hiện các hoạt động bất thường hoặc tấn công mạng trong một biển dữ liệu khổng lồ.

---

## 1. SIEM Rules là gì?

Về bản chất, các quy tắc SIEM là các **truy vấn tìm kiếm (search queries)** được thiết lập để quét qua các dữ liệu được nạp vào hệ thống (theo thời gian thực hoặc dữ liệu lịch sử) nhằm tìm kiếm các hoạt động cụ thể.

Có hai hình thức chính của quy tắc SIEM:
* **Quy tắc có sẵn (Out-of-the-box):** Do nhà cung cấp SIEM cung cấp để phát hiện các kiểu tấn công phổ biến và các mẫu hành vi nghi vấn chung.
* **Quy tắc do con người viết (Human-written):** Do các chuyên gia phòng thủ (Defenders) trong tổ chức tự xây dựng dựa trên sự hiểu biết về môi trường mạng cụ thể của họ (cái gì là bình thường và cái gì là bất thường đối với tổ chức đó).

**Cơ chế hoạt động:**
Khi một truy vấn khớp với một mẩu dữ liệu, các hành động khác nhau sẽ được kích hoạt như:
* Tạo cảnh báo (Alert).
* Gửi email cho đội ngũ bảo mật.
* Ghi lại hoạt động vào một vị trí riêng biệt để theo dõi.
* **Tần suất:** Các quy tắc có thể chạy liên tục (phát hiện thời gian thực) hoặc chạy theo lịch trình cụ thể (ví dụ: hàng ngày hoặc hàng tuần).

---

## 2. Các ví dụ về chức năng của SIEM Rule

Hệ thống có thể tạo quy tắc để giám sát vô số hoạt động, miễn là dữ liệu log được nạp vào đầy đủ. Các nhóm giám sát phổ biến bao gồm:

### Hoạt động Tài khoản và Xác thực
* Theo dõi các lần đăng nhập thất bại (Failed logon attempts).
* Đăng nhập (thành công hoặc thất bại) vào các tài khoản đã bị vô hiệu hóa.
* Sử dụng các tài khoản đặc quyền (Local Admin, Domain Admin, Administrator).
* Thay đổi SID (Security Identifier) của tài khoản - một dấu hiệu tiềm tàng của việc leo thang đặc quyền.

### Thực thi Tiến trình (Process Execution)
* Thực thi từ các vị trí bất thường: Ví dụ như từ thư mục tạm (temp) hoặc bộ nhớ đệm trình duyệt (browser cache) – dấu hiệu của mã độc hoặc cơ chế duy trì sự hiện diện.
* Mối quan hệ tiến trình khả nghi: Ví dụ Microsoft Word khởi chạy tiến trình con là CMD hoặc PowerShell (có thể là do macro độc hại đang thực thi mã).
* Các mã băm (Hash) độc hại đã biết: Đối chiếu MD5, SHA1, SHA256 với danh sách các tệp tin độc hại đã được xác nhận.

### Hoạt động Mạng
* Quét cổng (Port scans).
* Liệt kê dịch vụ (Service enumeration).
* Dò quét máy chủ (Host discovery).

---

## 3. Giảm thiểu Cảnh báo giả (False Positive) và Điều chỉnh (Tuning)

**False Positive (Cảnh báo giả)** là những cảnh báo được tạo ra nhưng thực tế không phải là sự kiện độc hại. Nếu quy tắc quá nhạy, nó sẽ gây ra tình trạng "nhiễu" (noisy).

### Thiết lập Ngưỡng (Thresholds)
Thay vì báo động cho mỗi lần đăng nhập sai (vốn là việc bình thường khi người dùng quên mật khẩu), ta có thể đặt ngưỡng:
* *Ví dụ:* Nếu một tài khoản đăng nhập sai **10 lần trong vòng 10 phút**, lúc đó hệ thống mới tạo cảnh báo. Điều này giúp nhận diện các cuộc tấn công dò mật khẩu (Brute force hoặc Dictionary attacks).

### Loại trừ (Exclusions/Whitelisting)
Trong một số trường hợp, các hoạt động trông giống như tấn công nhưng lại là hợp lệ.
* *Ví dụ:* Công ty sử dụng một máy quét lỗ hổng (Vulnerability Scanner). Máy này sẽ gửi lưu lượng truy cập đến mọi IP trong mạng để kiểm tra. Quy tắc giám sát "quét mạng" sẽ bị kích hoạt liên tục.
* *Giải pháp:* Đội ngũ bảo mật sẽ cấu hình quy tắc để **loại trừ IP nguồn** của máy quét đó. SIEM vẫn ghi nhận dữ liệu nhưng sẽ không tạo cảnh báo khi thấy IP này hoạt động.

---

## 4. Viết truy vấn và Cảnh báo

Việc học cách viết truy vấn là bước quan trọng tiếp theo. Các nền tảng phổ biến bao gồm:
* **Splunk:** Một trong những giải pháp SIEM hàng đầu để viết truy vấn tìm kiếm thông tin trong tập dữ liệu lớn.
* **ELK Stack (Elasticsearch, Logstash, Kibana):** Một giải pháp thay thế mã nguồn mở mạnh mẽ để tạo các quy tắc phát hiện.

# Tìm hiểu về Sigma Rules trong SIEM

## 1. Sigma là gì?
Sigma là một định dạng chữ ký (signature format) mở và có tính chất chung (generic), cho phép người dùng mô tả các sự kiện log (log events) có liên quan một cách trực tiếp và dễ dàng. 

* **Tính linh hoạt:** Định dạng quy tắc của Sigma rất linh hoạt, dễ viết và có thể áp dụng cho bất kỳ loại tệp log nào.
* **Mục đích chính:** Cung cấp một cấu trúc chuẩn hóa để các nhà nghiên cứu hoặc phân tích bảo mật có thể mô tả các phương pháp phát hiện (detection methods) và chia sẻ chúng với cộng đồng.

## 2. Cách thức hoạt động và Chuyển đổi
Sigma đóng vai trò như một ngôn ngữ chung giữa các nền tảng SIEM khác nhau:
* **Quy trình thuận:** Các quy tắc được viết bằng ngôn ngữ Sigma, sau đó sử dụng bộ chuyển đổi (Sigmac) để xuất ra định dạng quy tắc chính xác cho nhiều nền tảng SIEM khác nhau.
* **Quy trình nghịch:** Quá trình này có thể đảo ngược, cho phép các chuyên gia bảo mật xuất các quy tắc từ định dạng của nhà cung cấp (vendor format) sang định dạng Sigma để các đội ngũ sử dụng SIEM khác có thể dùng được.


## 3. Các nền tảng hỗ trợ Sigma
Sigma hỗ trợ rộng rãi các nền tảng phổ biến bao gồm:
* **Splunk** 
* **QRadar** 
* **ArcSight** 
* **Elasticsearch** (bao gồm Elastalert, Query strings, DSL, Watcher, và Kibana) 
* **Logpoint** 

## 4. Lợi ích của việc sử dụng Sigma
* **Khả năng chia sẻ:** Giúp phương pháp phát hiện của bạn có thể chia sẻ được với cộng đồng.
* **Tránh phụ thuộc nhà cung cấp (Vendor Lock-in):** Bạn có thể viết các tìm kiếm SIEM bằng Sigma để linh hoạt thay đổi giải pháp SIEM mà không bị mất các quy tắc tùy chỉnh đã xây dựng.
* **Tái sử dụng:** Cho phép người khác lặp lại công việc của bạn và xây dựng các quy tắc phát hiện dựa trên đó.
* **Cộng tác cộng đồng:** Dễ dàng chia sẻ chữ ký trong các cộng đồng tình báo mối đe dọa (như ISACs hoặc qua MISP).

## 5. Ví dụ về Quy tắc Sigma (Phát hiện Web Shell)
Tài liệu đưa ra ví dụ về một quy tắc Sigma dùng để phát hiện máy chủ web bị xâm nhập và đang chạy web shell.

* **Cơ chế hoạt động:** Quy tắc sử dụng phương pháp khớp từ khóa (keyword matching) đối với chuỗi URL.
* **Kịch bản phát hiện:** Nếu một kẻ tấn công truy cập vào web shell và cố gắng thực thi các lệnh hệ điều hành (ví dụ: `whoami`), các lệnh này thường sẽ được bao gồm trong một yêu cầu HTTP POST gửi đến máy chủ.
* **Độ chính xác:** Tỷ lệ cảnh báo giả (false positives) thấp vì người dùng bình thường cực kỳ hiếm khi đưa các lệnh hệ điều hành vào yêu cầu URL POST.

## 6. Tài nguyên tham khảo
Bạn có thể tìm thấy các quy tắc thực tế tại:
* Trang GitHub của Florian Roth (Neo23x0).https://github.com/Neo23x0/sigma

* Kho lưu trữ quy tắc Sigma chính thức trên GitHub.https://github.com/SigmaHQ/sigma/tree/master/rules

# Tổng quan về Regular Expression (Regex)

Regular Expression, hay còn gọi là **Regex**, là một chuỗi văn bản được sử dụng để tạo ra các **mẫu tìm kiếm (search pattern)**. Regex cực kỳ mạnh mẽ trong việc tìm kiếm văn bản, xác thực dữ liệu đầu vào (như email, số điện thoại), hoặc thay thế và sắp xếp lại nội dung văn bản.

## 1. Ứng dụng của Regex
Regex được tích hợp và sử dụng rộng rãi trong nhiều lĩnh vực:
* **Trình chỉnh sửa văn bản và mã nguồn:** Tìm kiếm và thay thế nhanh.
* **Công cụ tìm kiếm & API:** Lọc dữ liệu chính xác.
* **Xác thực dữ liệu người dùng:** Kiểm tra định dạng form (email, mật khẩu).
* **Phân tích dữ liệu & Web Scraping:** Trích xuất thông tin từ các trang web hoặc tệp log.

## 2. Các "Flavor" (Biến thể) của Regex
Mặc dù hầu hết các Regex hiện đại đều dựa trên ngôn ngữ lập trình Perl, nhưng tùy vào ứng dụng hoặc hệ điều hành mà chúng có những cách triển khai khác nhau:
* **Linux:** Có hai công cụ chính là **BRE (Basic Regular Expression)** và **ERE (Extended Regular Expression)**.
* **Grep:** Là công cụ tìm kiếm văn bản phổ biến trong Linux (viết tắt của "global regular expression print"). Để sử dụng Regex mở rộng với grep, ta dùng cờ `-E`.
    * *Cú pháp:* `grep -E "(regex)"`

## 3. Cú pháp viết Query Regex cơ bản

### Khớp chính xác và Toán tử OR
* **Khớp chính xác:** Regex `(but)` sẽ khớp chính xác từ "but" trong câu.
* **Toán tử OR (`|`):** Cho phép khớp một trong nhiều lựa chọn.
    * Ví dụ: `(g|f)at` sẽ khớp với "gat" hoặc "fat".
* **Dấu ngoặc vuông `[]`:** Tương tự toán tử OR nhưng dùng cho từng ký tự.
    * Ví dụ: `[gf]at` cũng sẽ khớp với "gat" hoặc "fat".

### Phạm vi ký tự (Ranges)
Sử dụng dấu ngoặc vuông để xác định một nhóm ký tự:
* `[a-z]`: Khớp tất cả các chữ cái viết thường từ a đến z.
* `[A-Z]`: Khớp tất cả các chữ cái viết hoa từ A đến Z.
* `[0-9]`: Khớp tất cả các số từ 0 đến 9.
* `[a-zA-Z]`: Khớp mọi chữ cái (cả hoa và thường).

### Phủ định (Negation)
Sử dụng ký tự `^` bên trong dấu ngoặc vuông để loại trừ:
* `[^a-z]`: Khớp bất kỳ thứ gì **không phải** chữ cái viết thường.
* `[^0-9]`: Khớp bất kỳ thứ gì **không phải** là số.


## 4. Character Classes (Lớp ký tự)
Đây là các ký tự đại diện giúp viết Regex ngắn gọn hơn. **Lưu ý:** Chữ cái viết hoa thường có ý nghĩa phủ định của chữ cái viết thường tương ứng.

| Regex | Mô tả |
| :--- | :--- |
| `\s` | Khớp ký tự khoảng trắng (dấu cách, tab). |
| `\S` | Khớp bất kỳ ký tự nào **không phải** khoảng trắng. |
| `\d` | Khớp bất kỳ ký tự chữ số nào. |
| `\D` | Khớp bất kỳ ký tự nào **không phải** chữ số. |
| `\w` | Khớp ký tự từ (bao gồm chữ cái và số - alphanumeric). |
| `\W` | Khớp ký tự **không phải** ký tự từ (ký tự đặc biệt, dấu câu). |
| `\b` | Khớp ranh giới từ (khoảng cách giữa từ và dấu câu/khoảng trắng). |

## 5. Nhóm, Bộ định lượng và Neo (Anchors)

* **Dấu ngoặc đơn `()`:** Dùng để nhóm các phần tử của biểu thức lại với nhau.
    * Ví dụ: `([a-z] \d+)` khớp với chữ cái thường theo sau là một hoặc nhiều số.
* **Dấu sao `*`:** Khớp ký tự đứng trước nó **0 hoặc nhiều lần**.
    * Ví dụ: `122*3` khớp với 123, 1223, 12223...
* **Dấu cộng `+`:** Khớp ký tự đứng trước nó **ít nhất 1 lần hoặc nhiều hơn**.
* **Dấu ngoặc nhọn `{}`:** Lặp lại ký tự đứng trước theo số lần cụ thể.
    * Ví dụ: `o{2}` trong từ "Book" sẽ khớp với "oo".
* **Wildcard `.`:** Khớp với **bất kỳ** ký hiệu đơn lẻ nào.
* **Dấu `.*`:** Khớp với bất kỳ ký hiệu nào, lặp lại bất kỳ số lần nào.
* **Dấu mũ `^`:** Khớp tại **vị trí bắt đầu** của một dòng hoặc chuỗi.
* **Dấu đô la `$`:** Khớp tại **vị trí kết thúc** của một dòng hoặc chuỗi.
* **Dấu hỏi `?`:** Ký tự tùy chọn (có thể có hoặc không).
    * Ví dụ: `docx?` sẽ khớp với cả "docx" và "doc".

## 6. Ví dụ thực tế (Real-world Regex)

* **Khớp Hostname website:** `www.[\w-]+\.([\w.-]+)+`
* **Khớp Email:** `([a-zA-Z0-9_\-\.]+)@([a-zA-Z0-9_\-\.]+)\.([a-zA-Z]{2,5})`
* **Khớp số điện thoại Mỹ (123-123-1234):** `([0-9]{3})-([0-9]{3})-([0-9]{4})`
* **Khớp số điện thoại Anh (07123456789):** `((\+44)?( )?(\(\d\))? ?)(0) ?[0-9]{3,4} ?[0-9]{3}`

---
## 7. Công cụ thực hành
Để rèn luyện kỹ năng viết Regex, bạn có thể sử dụng các website miễn phí sau:
1. **Regex101.com:** Hỗ trợ giải thích chi tiết từng phần của query.
2. **Regexr.com:** Giao diện trực quan, dễ sử dụng.
3. **Ihateregex.io:** Kho tàng các mẫu Regex có sẵn cho các tác vụ phổ biến.

