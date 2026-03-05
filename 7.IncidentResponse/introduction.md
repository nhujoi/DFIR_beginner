# Tìm hiểu về Incident Response (Ứng phó sự cố)

Dựa trên tài liệu đào tạo Blue Team Level 1, Incident Response (IR) là một thành phần thiết yếu trong chiến lược bảo mật của bất kỳ tổ chức nào. Dưới đây là chi tiết về khái niệm này:

## 1. Định nghĩa Incident Response
Incident Response (Ứng phó sự cố) được định nghĩa là phương pháp luận mà một tổ chức sử dụng để phản ứng và quản lý một cuộc tấn công mạng. Đây là một cách tiếp cận mang tính phản ứng (reactive), có mối liên hệ chặt chẽ với các nỗ lực phục hồi sau thảm họa (disaster recovery).

## 2. Tại sao Incident Response lại quan trọng?
Khi một cuộc tấn công mạng xảy ra thành công, các hành động được thực hiện bởi các chuyên gia bảo mật có ý nghĩa cực kỳ quan trọng nhằm:
* **Hạn chế thiệt hại:** Ngăn chặn kẻ tấn công gây thêm tổn thất cho hệ thống.
* **Phục hồi nhanh chóng:** Đưa các hoạt động trở lại bình thường càng nhanh càng tốt để giảm thiểu tác động tiêu cực đến hoạt động kinh doanh.
* **Tiết kiệm chi phí:** Phản ứng một cách có tổ chức với các nguồn lực phù hợp sẽ giúp giảm thời gian và chi phí phục hồi.
* **Cải thiện phòng thủ:** Thông qua việc ghi chép chi tiết và cập nhật các kế hoạch ứng phó (runbooks), tổ chức có thể học hỏi từ những điểm yếu của mình để đối phó tốt hơn với các cuộc tấn công trong tương lai.

## 3. Phân biệt Sự kiện (Event) và Sự cố (Incident)
* **Security Events (Sự kiện bảo mật):** Xảy ra hàng ngày và thường được xử lý bởi các nhà phân tích bảo mật (thường làm việc trong Trung tâm điều hành an ninh - SOC).
* **Security Incidents (Sự cố bảo mật):** Là những tình huống nghiêm trọng hơn, đòi hỏi sự can thiệp của các chuyên gia ứng phó sự cố chuyên trách.

## 4. Vòng đời ứng phó sự cố (NIST SP 800-61 r2)
Quy trình ứng phó sự cố thường tuân theo tiêu chuẩn của NIST với các giai đoạn chính:
* **Giai đoạn Chuẩn bị (Preparation):** Xem xét và triển khai các kiểm soát bảo mật để giảm khả năng và tác động của một cuộc tấn công.
* **Giai đoạn Phát hiện và Phân tích (Detection and Analysis):** Nhận diện dấu hiệu tấn công và xác định mức độ nghiêm trọng.
* **Giai đoạn Ngăn chặn, Tiêu diệt và Khôi phục (Containment, Eradication, and Recovery):** Cô lập mối đe dọa, loại bỏ hoàn toàn mã độc/kẻ tấn công khỏi hệ thống và khôi phục dữ liệu/dịch vụ.

## 5. Đội ngũ CSIRT (Computer Security Incident Response Team)
Các tổ chức lớn thường có một đội chuyên trách gọi là CSIRT. Đội ngũ này không chỉ bao gồm các chuyên gia bảo mật mà còn có sự tham gia của:
* Nhân viên CNTT (IT Staff).
* Đại diện từ bộ phận Nhân sự (HR).
* Bộ phận Truyền thông/Quan hệ công chúng (PR).
* Bộ phận Pháp lý (Legal).
* Các thành viên ban lãnh đạo cao cấp (C-suite).

# Tại sao Phản ứng Sự cố (Incident Response - IR) lại cần thiết?

Trong thế giới an ninh mạng, câu hỏi không phải là "Liệu chúng ta có bị tấn công không?" mà là "Khi nào chúng ta bị tấn công?". Incident Response (IR) chính là tấm khiên giúp doanh nghiệp trụ vững khi những kịch bản xấu nhất xảy ra.

---

## 1. Mục tiêu và Lợi ích cốt lõi
Mục tiêu chính của IR không phải là ngăn chặn mọi cuộc tấn công (điều đó là bất khả thi), mà là **giảm thiểu thiệt hại** và đưa doanh nghiệp trở lại trạng thái hoạt động bình thường nhanh nhất có thể.

* **Giảm thiểu tác động:** Khi một cuộc tấn công thành công, IR giúp khoanh vùng vùng ảnh hưởng, ngăn chặn sự lây lan.
* **Duy trì vận hành:** Đảm bảo các hoạt động kinh doanh ít bị gián đoạn nhất, tránh tình trạng tê liệt hệ thống kéo dài.

---

## 2. Hậu quả của việc thiếu quy trình IR hiệu quả
Một cuộc tấn công mạng thành công mà không được xử lý đúng cách sẽ dẫn đến những hệ lụy khủng khiếp:

* **Rò rỉ dữ liệu (Data Breaches):** Thông tin nhạy cảm của tổ chức bị đánh cắp và đưa ra ngoài.
* **Mất niềm tin:** Khách hàng sẽ rời bỏ nếu họ cảm thấy dữ liệu cá nhân của mình không được bảo vệ.
* **Thiệt hại tài chính trực tiếp:** Chi phí khôi phục hệ thống bị nhiễm mã độc, chi phí thuê đội ngũ bảo mật bên ngoài để ứng cứu.
* **Biến động thị trường:** Giá cổ phiếu có thể sụt giảm ngay lập tức sau khi thông tin bị tấn công được công bố.

---

## 3. Áp lực từ Pháp lý và Quy định (Regulatory Fines)
Các tổ chức phải đối mặt với những khoản phạt khổng lồ nếu vi phạm các quy định bảo mật (như GDPR của EU). Đối với các doanh nghiệp nhỏ, những khoản phạt này có thể dẫn đến việc phá sản hoặc buộc phải thay đổi toàn bộ mô hình kinh doanh.

**Một số ví dụ thực tế về mức phạt:**
| Tổ chức | Thời điểm | Mức phạt (Dự kiến/Thực tế) |
| :--- | :--- | :--- |
| **British Airways** | 07/2019 | £183 triệu (đề xuất) |
| **Marriott** | 07/2019 | £99 triệu (đề xuất) |
| **Equifax** | 09/2018 | £500,000 |
| **Uber** | 11/2018 | £385,000 |

---

## 4. IR không chỉ dành cho rò rỉ dữ liệu
Nhiều người lầm tưởng IR chỉ dùng khi bị hacker đánh cắp database, nhưng thực tế IR bao quát rất nhiều tình huống:

* **Mã độc & Ransomware:** Xử lý các hệ thống bị mã hóa đòi tiền chuộc.
* **Thất thoát thiết bị:** Nhân viên làm mất laptop làm việc (chứa dữ liệu công ty).
* **Sự cố danh tiếng:** Trang web của công ty bị thay đổi giao diện (defacement).
* **Rò rỉ nội bộ:** Nhân viên cố tình đánh cắp hoặc tuồn dữ liệu nhạy cảm ra ngoài.
* **Lộ lọt thông tin:** Tài khoản đăng nhập của nhân viên bị rao bán trên internet.

---

## 5. Tầm quan trọng của kế hoạch bằng văn bản
Việc chuẩn bị sẵn các kế hoạch phản ứng bằng văn bản giúp tổ chức:
1.  **Phản ứng nhanh:** Không bị lúng túng khi sự cố xảy ra.
2.  **Đúng quy trình:** Đảm bảo các bước ngăn chặn và loại bỏ mối đe dọa được thực hiện một cách chuyên nghiệp.
3.  **Giảm thiểu rủi ro:** Một quy trình chuẩn giúp kiểm soát mối đe dọa một cách thích hợp, tránh làm tình hình tồi tệ hơn.

> **Lời kết:** Incident Response là sự khác biệt giữa một "sự cố nhỏ" và một "thảm họa doanh nghiệp". Đầu tư vào IR chính là đầu tư vào sự sống còn của tổ chức.

# So sánh chi tiết: Security Events vs. Security Incidents

Mối quan hệ cốt lõi: Mọi **Sự cố bảo mật** đều là **Sự kiện bảo mật**, nhưng không phải mọi Sự kiện đều trở thành Sự cố.

---

## 1. Security Events (Sự kiện bảo mật)
Sự kiện bảo mật là bất kỳ hiện tượng nào có thể có tác động đến bảo mật, chẳng hạn như gây ra hư hại hoặc gián đoạn. Chúng xảy ra liên tục và thường được xử lý bằng các biện pháp kiểm soát tự động hoặc được ghi nhật ký (log) lại.

### Các ví dụ điển hình:
* **Email rác (Spam):** Có tiềm năng chứa liên kết độc hại hoặc phần mềm độc hại.
* **Quét lỗ hổng (Vulnerability Scan):** Kẻ xấu tìm kiếm điểm yếu để khai thác sau này.
* **Quét trinh sát (Reconnaissance Scan):** Thu thập thông tin về hệ thống của tổ chức.
* **Bất thường có lý do (Explained Anomaly):** Ví dụ: mạng bị gián đoạn do cấu hình sai thay vì bị tấn công.
* **Tấn công Brute-force đang diễn ra:** Đây được coi là sự kiện cho đến khi kẻ tấn công thực sự truy cập thành công.

---

## 2. Security Incidents (Sự cố bảo mật)
Sự cố bảo mật là những sự kiện đã thực sự dẫn đến thiệt hại cụ thể cho tổ chức (về dữ liệu, vận hành hoặc uy tín).

### Các ví dụ điển hình:
* **Nhiễm Mã độc tống tiền (Ransomware):** Từ một email spam (sự kiện) dẫn đến việc dữ liệu bị mã hóa (sự cố).
* **Vi phạm dữ liệu (Data Breach):** Từ việc quét lỗ hổng (sự kiện) dẫn đến việc kẻ xấu xâm nhập và lấy cắp dữ liệu (sự cố).
* **Bất thường chưa rõ nguyên nhân (Unexplained Anomaly):** Được phân loại là sự cố ngay lập tức vì tiềm ẩn nguy cơ độc hại chưa được xác định.
* **Xâm nhập thành công:** Khi một cuộc tấn công Brute-force giúp kẻ xấu vào được hệ thống để sửa đổi trang web hoặc xem cơ sở dữ liệu.

---

## 3. Bảng so sánh nhanh

| Đặc điểm | Security Event (Sự kiện) | Security Incident (Sự cố) |
| :--- | :--- | :--- |
| **Định nghĩa** | Bất kỳ thay đổi/hoạt động nào có ý nghĩa bảo mật. | Sự kiện gây ra thiệt hại thực tế cho tổ chức. |
| **Tác động** | Tiềm năng (Có thể xảy ra). | Thực tế (Đã xảy ra). |
| **Người xử lý** | Security Analysts (SOC). | Incident Responders / CSIRT. |
| **Công cụ hỗ trợ** | SIEM, IDS, Automated controls. | Nâng cao (Forensics, Analysis tools). |

---

## 4. Cách thức xử lý
* **Phân tích cảnh báo:** Không phải mọi cảnh báo từ SIEM hay IDS đều là sự cố. Phần lớn là các sự kiện có thể quản lý được hoặc thậm chí là "Dương tính giả" (False Positive).
* **Vai trò:** Các chuyên gia ứng phó sự cố (Incident Responders) sẽ thực hiện các bước điều tra nâng cao, ngăn chặn và khắc phục khi một sự kiện leo thang thành sự cố nghiêm trọng.

# Vòng đời Ứng phó Sự cố (NIST SP 800-61r2)

Vòng đời ứng phó sự cố (Incident Response Lifecycle) theo NIST SP 800-61r2 là một quy trình lặp đi lặp lại và liên tục, bao gồm bốn giai đoạn chính nhằm giúp tổ chức xử lý các sự cố an ninh mạng và ngăn chặn chúng tái diễn trong tương lai.


---

## 1. Giai đoạn Chuẩn bị (Preparation)
Đây là giai đoạn quan trọng nhất để thiết lập nền tảng cho việc ứng phó sự cố. Nếu thiếu đội ngũ, nguồn lực hoặc tài liệu phù hợp, quy trình ứng phó sẽ dễ dẫn đến thất bại.

Giai đoạn này tập trung vào hai nhóm chính:
### Chuẩn bị cho các sự cố
* **Thông tin liên lạc:** Duy trì danh sách liên hệ của tất cả các bên liên quan (stakeholders).
* **Phòng tác chiến (War room):** Thiết lập một không gian tập trung để liên lạc và phối hợp.
* **Tài liệu & Baselines:** Có sẵn các tài liệu hướng dẫn và thông số vận hành tiêu chuẩn của hệ thống.
* **Thiết bị:** Trang bị các bộ công cụ cần thiết cho ứng phó sự cố, chẳng hạn như bộ công cụ pháp y kỹ thuật số (digital forensic toolkits).

### Chủ động ngăn chặn sự cố
* Thực hiện đánh giá rủi ro định kỳ.
* Tăng cường bảo mật cho thiết bị đầu cuối (Client) và máy chủ (Server).
* Thiết lập các chương trình đào tạo và nâng cao nhận thức cho người dùng.

---

## 2. Giai đoạn Phát hiện và Phân tích (Detection & Analysis)
Giai đoạn này nhằm mục đích cảnh báo cho đội ứng cứu sự cố (CSIRT) về một sự kiện đang diễn ra và xác định bản chất của nó.

### Phát hiện (Detection)
Sử dụng các công cụ giám sát để cảnh báo khi có sự cố xảy ra:
* Hệ thống phát hiện và ngăn chặn xâm nhập (IDPS).
* Phần mềm diệt virus, chống spam/malware.
* Các giải pháp giám sát log (nhật ký hệ thống).

### Phân tích (Analysis)
Đây thường là bước phức tạp nhất, bao gồm:
* Xác định cách thức cuộc tấn công ban đầu diễn ra và cách nó di chuyển trong mạng.
* Sử dụng hồ sơ mạng, cơ sở tri thức và chính sách lưu trữ log để hỗ trợ phân tích.
* **Ưu tiên hành động:** Xác định mức độ ưu tiên của các bước cần thực hiện.
* **Thông báo:** Liên lạc với các cơ quan có thẩm quyền, ban quản lý, bộ phận nhân sự và pháp lý theo **Kế hoạch Truyền thông (Communication Plan)**.

---

## 3. Ngăn chặn, Loại bỏ và Khôi phục (Containment, Eradication & Recovery)
Giai đoạn này tập trung vào việc hạn chế thiệt hại và đưa hệ thống trở lại trạng thái bình thường.

### Ngăn chặn (Containment)
Chiến lược ngăn chặn được quyết định dựa trên các tiêu chí:
* Khả năng gây thiệt hại và mất mát tài nguyên.
* Nhu cầu bảo tồn bằng chứng.
* Tính khả dụng của dịch vụ và thời gian/nguồn lực cần thiết.
* Hiệu quả và thời hạn của giải pháp.

### Loại bỏ và Khôi phục (Eradication & Recovery)
* **Loại bỏ:** Xóa bỏ mã độc, reset thông tin đăng nhập của các tài khoản bị xâm nhập hoặc xây dựng lại máy chủ từ các bản sao lưu sạch.
* **Khôi phục:** Đưa hệ thống về trạng thái trước khi bị tấn công. Điều này bao gồm việc khắc phục các lỗ hổng đã bị khai thác, cài đặt bản vá và thắt chặt an ninh mạng.

---

## 4. Hoạt động sau sự cố (Post-Incident Activity)
Mục tiêu cốt lõi của giai đoạn này là học hỏi và cải thiện hệ thống để đối phó với các mối đe dọa mới.

### Bài học kinh nghiệm (Lessons Learned)
NIST khuyến nghị tổ chức một cuộc họp để giải quyết các câu hỏi quan trọng:
* Chính xác thì chuyện gì đã xảy ra và xảy ra khi nào?
* Đội ngũ nhân viên và ban quản lý đã xử lý tốt đến mức nào?
* Những thông tin nào cần được cung cấp sớm hơn?
* Có hành động nào gây cản trở quá trình khôi phục không?
* Cần làm gì khác đi nếu sự cố tương tự xảy ra lần nữa?
* Các chỉ số (indicators) nào cần được theo dõi trong tương lai?

> **Lưu ý:** Kết quả từ cuộc họp này phải được đưa ngược trở lại **Giai đoạn Chuẩn bị** để hoàn thiện chu kỳ ứng phó và tăng cường khả năng phòng thủ của tổ chức.

# Tìm hiểu về CSIRT và CERT trong lĩnh vực Phản ứng sự cố (Incident Response)

Trong bối cảnh các cuộc tấn công mạng diễn ra hàng ngày, các tổ chức và chính phủ cần những đội ngũ chuyên biệt để ứng phó hiệu quả. Đó là lý do CSIRT và CERT ra đời.

## 1. Định nghĩa và Vai trò cốt lõi
* **CERT (Cyber Emergency Response Team):** Đội ứng cứu khẩn cấp không gian mạng.
* **CSIRT (Cyber Security Incident Response Team):** Đội phản ứng sự cố an ninh mạng.

**Nhiệm vụ chính:**
* Điều phối và phản ứng với các sự cố bảo mật CNTT.
* Đánh giá mức độ tác động của sự cố đối với tổ chức hoặc cơ quan chính phủ.

## 2. Thành phần của một đội phản ứng sự cố
Một CSIRT thường không chỉ có các kỹ thuật viên bảo mật mà còn bao gồm các bên liên quan từ nhiều bộ phận khác nhau để đảm bảo khả năng xử lý toàn diện:
* Hạ tầng (Infrastructure) và Mạng (Networking).
* Pháp lý (Legal) và Quan hệ công chúng (Public Relations).
* Truyền thông (Communications) và Bảo mật (Security).

## 3. Tại sao CSIRT/CERT lại quan trọng?
Các đội ngũ này đóng vai trò sống còn thông qua các chức năng:
* **Trung tâm chỉ huy:** Là điểm liên lạc tập trung, nơi mọi thông tin về sự cố được xử lý.
* **Nâng cao nhận thức:** Thúc đẩy đào tạo bảo mật (ví dụ: diễn tập chống lừa đảo - phishing).
* **Phòng ngừa và Lập kế hoạch:** Nghiên cứu lỗ hổng mới và lập kế hoạch giảm thiểu rủi ro trước khi bị khai thác.
* **Đo lường hiệu quả:** Xác định các chỉ số như **MTTR** (Mean Time to Repair - Thời gian trung bình để sửa chữa) và **MDT** (Mean Downtime - Thời gian chết trung bình) cho tài sản của công ty.
* **Chia sẻ cộng đồng:** Cung cấp thông tin hữu ích cho các CSIRT khác và cộng đồng an ninh mạng toàn cầu.

## 4. Phân biệt Công và Tư (Public vs. Private)
Mặc dù có nhiều tên gọi khác nhau (SIRT, IRT, CSIRC), mục tiêu cuối cùng của chúng là như nhau. Tuy nhiên, có sự khác biệt nhỏ trong cách sử dụng thuật ngữ:

| Thuật ngữ | Phạm vi áp dụng thường thấy | Ví dụ tiêu biểu |
| :--- | :--- | :--- |
| **CERT** | Các đội ngũ được công nhận ở cấp quốc gia. | US-CERT (Mỹ), CERT-UK (Anh), AusCERT (Úc). |
| **CSIRT** | Các đội ngũ nội bộ của doanh nghiệp. | Xử lý các vi phạm an ninh nội bộ. |

## 5. Case Study: CERT New Zealand (CERT NZ)
* **Lịch sử:** Các CERT chính phủ bắt đầu phát triển mạnh từ đầu những năm 2000.
* **Mục tiêu:** Bảo vệ doanh nghiệp và cá nhân trong nước, đồng thời hỗ trợ quốc tế.
* **Tính minh bạch:** CERT NZ thường xuyên công bố báo cáo hàng quý và hàng năm về các hoạt động và sự cố đã xử lý. 
* **Dữ liệu (Ví dụ 2018):** Họ đã xử lý hàng ngàn báo cáo về lừa đảo (phishing), truy cập trái phép và các báo cáo lỗ hổng bảo mật, giúp giảm thiểu tổn thất tài chính đáng kể.

# Blue Team Level 1 (BTL1) - Incident Response Further Reading

## 1. Thông tin chung
* **Chứng chỉ:** Blue Team Level 1 Certification (Standard)
* **Chương:** Incident Response Domain
* **Bài học:** IR1) Introduction to Incident Response > Further Reading Material
* **Mục đích:** Cung cấp tài liệu đọc thêm để củng cố kỹ năng Incident Response (IR) và chuẩn bị cho kỳ thi thực hành BTL1.

---

## 2. Danh sách tài liệu tham khảo (Resources)

Học viên được khuyến khích quay lại bài học này sau khi đã hoàn thành toàn bộ Domain Incident Response.

| Tài liệu / Chủ đề | Liên kết tham khảo |
| :--- | :--- |
| **Incident Response Resources** (Runbooks, sách, khung làm việc, nghề nghiệp) | https://www.incidentresponse.com/resources/ |
| **Incident Response Resources From Infosec Institute** | http://resources.infosecinstitute.com/category/incident-response-resources/ |
| **A Curated List of Tools for Incident Response** (Awesome IR) | https://github.com/meirwatt/awesome-incident-response |
| **Incident Response Tools by AT&T Cybersecurity** | https://cybersecurity.att.com/resource-center/ebook/insider-guide-to-incident-response/incident-response-tools |
| **Proactive Incident Response by Secureworks** | https://www.secureworks.com/centers/proactive-incident-response |
| **Incident Handler's Handbook by SANS** | https://www.sans.org/reading-room/whitepapers/incident/paper/33901 |
| **Ultimate Guide to Cybersecurity Incident Response by Tech Target** | https://searchsecurity.techtarget.com/ultimate-guide-to-incident-response-and-management |
| **A Beginners Guide to Open Source Incident Response Tools and Resources** | https://www.cybersecurity-insiders.com/beginners-guide-to-open-source-incident-response-tools-and-resources/ |

---

## 3. Cấu trúc chương Incident Response (IR)
Chương này bao gồm các chủ đề quan trọng sau:
* **IR1: Introduction to Incident Response**
    * Định nghĩa Incident Response là gì? Tại sao cần IR?
    * Phân biệt Sự kiện bảo mật (Security Events) vs Sự cố bảo mật (Security Incidents).
    * Vòng đời ứng cứu sự cố (NIST SP 800-61 r2).
    * Giải thích về CSIRT và CERT.
    * Thuật ngữ IR (Glossary).
* **IR2: Preparation Phase** (Giai đoạn chuẩn bị).
* **IR3: Detection and Analysis Phase** (Giai đoạn phát hiện và phân tích).
* **IR4: Containment, Eradication, and Recovery Phase** (Giai đoạn ngăn chặn, xử lý và phục hồi).
* **IR5: Lessons Learned and Reporting** (Bài học kinh nghiệm và báo cáo).
* **IR6: MITRE ATT&CK**.

---

## 4. Các chủ đề liên quan khác trong khóa học
* **Digital Forensics (DF):** Volatility (DF6), Autopsy (DF7).
* **SIEM Domain:** Giới thiệu về SIEM, Logging, Aggregation, Correlation, và sử dụng Splunk.
* **BTL1 Exam:** Hướng dẫn chuẩn bị thi, cách sử dụng RDP/SSH và quy trình bắt đầu bài thi.

---

## 5. Liên hệ đóng góp
Nếu học viên có thêm tài liệu hữu ích muốn bổ sung vào danh sách, có thể liên hệ qua email:
* **Email:** BTL1@securityblue.team
* **Tiêu đề:** Incident Response Domain Further Reading
# Incident Response Domain - Glossary (BTL1)

Tài liệu này tổng hợp các thuật ngữ và từ viết tắt quan trọng được sử dụng trong lĩnh vực Ứng phó sự cố (Incident Response).

---

### 1. Các tổ chức và Đội ngũ
* **CERT (Computer Emergency Response Team):** Đội ứng cứu khẩn cấp máy tính. Đây là nhóm chịu trách nhiệm phản ứng với các sự cố an ninh máy tính. Hầu hết các chính phủ đều có CERT riêng để nghiên cứu và phòng thủ an ninh.
* **CSIRT (Computer Security Incident Response Team):** Đội phản ứng sự cố an ninh máy tính. Một tên gọi khác cho các nhóm phản ứng sự cố, bao gồm nhân sự từ bộ phận an ninh, IT và các phòng ban quan trọng khác như Pháp lý, Truyền thông, Nhân sự.
* **ISAC (Information Sharing and Analysis Center):** Trung tâm chia sẻ và phân tích thông tin. Tập hợp các tổ chức (thường trong cùng lĩnh vực công nghiệp) chia sẻ thông tin tình báo chiến thuật và chiến lược về các cuộc tấn công mạng nhằm cải thiện khả năng phòng thủ chung.

### 2. Kế hoạch và Chỉ dấu tấn công
* **IRP (Incident Response Plan):** Kế hoạch ứng phó sự cố. Tập hợp các hướng dẫn giúp nhân viên IT phát hiện, phản ứng và phục hồi sau các sự cố an ninh mạng (như tội phạm mạng, mất dữ liệu, gián đoạn dịch vụ).
* **IOC (Indicator of Compromise):** Chỉ dấu xâm phạm. Thông tin tình báo thu thập được từ hoạt động độc hại hoặc các vụ xâm nhập (Ví dụ: mã hash của tệp độc hại, tên tệp). Dùng để chia sẻ và đưa vào danh sách chặn (blocklist).
* **TTP (Tools, Techniques, and Procedures):** Công cụ, Kỹ thuật và Quy trình. MITRE định nghĩa hơn 240 chiến thuật độc nhất mà kẻ tấn công sử dụng, được gọi là các TTP.

### 3. Giải pháp Bảo mật Endpoint (Thiết bị đầu cuối)
* **EDR (Endpoint Detection and Response):** Giải pháp phát hiện và phản ứng tại điểm cuối. Nền tảng phân tích sử dụng các agent (trình thu thập) chạy trên thiết bị, liên tục gửi thông tin về máy chủ để tương quan dữ liệu, phát hiện bất thường và có thể tự động chặn kết nối.
* **AV (Antivirus Solution):** Giải pháp diệt virus. Cài đặt trên máy tính để phát hiện và loại bỏ phần mềm độc hại dựa trên nhận dạng (signature) hoặc hành vi bất thường (anomaly).
* **HIDS (Host Intrusion Detection System):** Hệ thống phát hiện xâm nhập trên máy chủ. Tạo cảnh báo khi phát hiện hoạt động nghi ngờ hoặc độc hại trên một thiết bị cụ thể.
* **HIPS (Host Intrusion Prevention System):** Hệ thống ngăn chặn xâm nhập trên máy chủ. Tương tự HIDS nhưng có khả năng thực hiện các hành động tự động để ngăn chặn mối đe dọa.

### 4. Giải pháp Bảo mật Mạng
* **DMZ (Demilitarized Zone):** Vùng phi quân sự. Một phân vùng mạng vật lý hoặc logic chứa và công khai các dịch vụ hướng ra bên ngoài của tổ chức với các mạng không tin cậy (như Internet).
* **IDS/IPS/IDPS (Intrusion Detection and Prevention System):** Hệ thống phát hiện và ngăn chặn xâm nhập. IDS dùng để báo cáo/cảnh báo, trong khi IPS có khả năng tự động dừng các nỗ lực tấn công.
* **NIDS (Network Intrusion Detection System):** Hệ thống phát hiện xâm nhập mạng. Giám sát lưu lượng mạng và tạo cảnh báo khi thấy hoạt động nghi ngờ.
* **NIPS (Network Intrusion Prevention System):** Hệ thống ngăn chặn xâm nhập mạng. Có khả năng chặn hoặc thiết lập lại (reset) các kết nối mạng độc hại.
* **FW (Firewall):** Tường lửa. Thiết bị phần cứng hoặc phần mềm sử dụng các quy tắc (rules) để cho phép hoặc hạn chế lưu lượng truy cập đi qua.
* **WAF (Web Application Firewall):** Tường lửa ứng dụng Web. Loại tường lửa phần mềm bảo vệ các máy chủ hướng Internet.
* **NGFW (Next-Generation Firewall):** Tường lửa thế hệ mới. Kết hợp tường lửa truyền thống với các chức năng lọc thiết kế mạng khác như kiểm soát gói tin sâu (deep packet inspection) và IPS.

### 5. Quản lý và Giám sát
* **SIEM (Security Information and Event Management):** Hệ thống quản lý sự kiện và thông tin an ninh. Tập trung nhật ký (logs) từ nhiều nguồn về một nơi để nhà phân tích có thể phân tích thời gian thực các cảnh báo an ninh.
* **GPO (Group Policy Object):** Đối tượng chính sách nhóm. Các thiết lập định nghĩa những hành động mà một hệ thống hoặc nhóm người dùng có thể thực hiện, giúp giảm thiểu rủi ro bằng cách giới hạn quyền hạn.
* **PCAP (Packet Capture):** Tệp lưu giữ thông tin lưu lượng mạng đã được ghi lại.
* **Sysmon (System Monitor):** Một bộ quy tắc mở rộng cung cấp dữ liệu chi tiết hơn so với Windows Event logs thông thường, hỗ trợ đắc lực cho việc giám sát, phòng thủ và săn tìm mối đe dọa (threat hunting).