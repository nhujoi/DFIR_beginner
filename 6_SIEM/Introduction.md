# Quản lý Thông tin Bảo mật (SIM)

Quản lý Thông tin Bảo mật, còn được gọi là SIM (Security Information Management), là phần mềm bảo mật chuyên dụng giúp thu thập, giám sát và phân tích dữ liệu cùng nhật ký sự kiện (event logs) được tạo ra từ tất cả các thiết bị bảo mật trong mạng (IDS, IPS, Phần mềm diệt virus, Tường lửa). Nó tạo điều kiện thuận lợi cho nhiệm vụ của các điều tra viên và đội ngũ bảo mật của một tổ chức bằng cách tập trung toàn bộ thông tin này vào một dịch vụ duy nhất.

## SIM có chức năng gì?

SIM chủ yếu đảm nhiệm việc thu thập và biên dịch thông tin liên quan đến hoạt động của mạng. Các thành phần này thu thập dữ liệu và nhật ký từ các thiết bị bên trong tổ chức, và thậm chí có thể thu thập thông tin từ một số thiết bị hoặc nguồn bên ngoài tổ chức (chẳng hạn như các dịch vụ nhận diện mối đe dọa công cộng và mạng lưới tương quan). Hệ thống sẽ tìm kiếm các quy luật (patterns) cho phép nó hiểu được hoạt động, vận hành và hành vi của các thiết bị này, sau đó tạo ra các báo cáo, biểu đồ và đồ thị để trình bày cho người dùng.

Một số hành động được thực hiện bởi SIM bao gồm:
* Giám sát các sự kiện trong thời gian thực.
* Gửi và tạo các cảnh báo và báo cáo.
* Tự động phản hồi các sự cố.
* Tương quan dữ liệu từ nhiều nguồn để cải thiện chất lượng của thông tin được trình bày.
* Biên dịch nhật ký sự kiện từ các tài nguyên khác nhau thông qua các tệp định dạng XML.

Tuy nhiên, mặc dù loại dịch vụ này cung cấp sự trợ giúp to lớn, cần làm rõ rằng đây không phải là các ứng dụng có thể hoạt động chính xác mà không cần sự can thiệp của nhân viên bảo mật và các thành viên trong tổ chức. Do đó, luôn có khuyến nghị rằng cần có một chính sách bảo mật tốt để bổ trợ cho hoạt động của loại sản phẩm này.

## Ưu điểm & Nhược điểm

SIM là dịch vụ mang lại nhiều lợi ích cho người dùng khi triển khai chúng trong tổ chức, một số lợi ích có thể kể đến như:
* Dễ dàng triển khai.
* Có thể lưu trữ và phân tích khối lượng dữ liệu lớn.
* Cho phép phân tích nhanh chóng và hiệu quả tất cả các sự kiện trong hệ thống.
* Tương quan nhật ký và sự kiện để cung cấp cái nhìn tổng quan chính xác nhất về hệ thống.
* Cho phép quản lý mối đe dọa dễ dàng (đánh giá, ngăn chặn và phân tích).

Tuy nhiên, cũng cần lưu ý một số nhược điểm có thể ảnh hưởng đến người dùng muốn áp dụng loại giải pháp này cho mạng của họ:
* Chúng có thể là những công cụ rất đắt đỏ.
* Không hoàn toàn chắc chắn rằng chúng có thể thích ứng hoàn hảo với mọi môi trường làm việc.
* Một số nhà cung cấp không hỗ trợ kỹ thuật đầy đủ cho loại dịch vụ này.

# Quản lý Sự kiện Bảo mật (SEM)

Quản lý Sự kiện Bảo mật, còn được gọi là SEM (Security Event Management), là một phần mềm bảo mật chuyên dụng trong việc xác định, thu thập, giám sát, đánh giá, thông báo và tương quan hóa theo thời gian thực các sự kiện và cảnh báo của hệ thống máy tính (thiết bị mạng, hệ thống bảo mật như IDS, IPS, Tường lửa, phần mềm chuyên dụng như Diệt virus, v.v.). Mục đích của nó là xác định các hành vi "đáng ngờ" bên trong hệ thống, nhằm cung cấp một phản hồi hiệu quả và kịp thời từ đội ngũ bảo mật đối với bất kỳ sự cố nào xảy ra trong mạng.

## SEM có chức năng gì?

SEM chủ yếu chịu trách nhiệm giám sát và phân tích theo thời gian thực các sự kiện hiện có trong một hệ thống công nghệ thông tin (CNTT), nhằm tìm kiếm bất kỳ loại hành vi bất thường nào có thể đồng nghĩa với việc lây nhiễm, sự cố hoặc mối đe dọa đang tồn tại trong hệ thống. Một số hành động do phần mềm SEM thực hiện bao gồm:

* Giám sát các sự kiện theo thời gian thực.
* Thu thập các sự kiện bảo mật trên các thiết bị và ứng dụng trong hệ thống.
* Tương quan hóa các sự kiện để cung cấp một bức tranh rõ ràng về hệ thống thông tin. Phân tích nhật ký (logs) theo mức độ quan trọng của chúng.
* Phản hồi sự cố theo thời gian thực.

Các hệ thống này phân tích tỉ mỉ từng bản ghi thu thập được, sử dụng các thuật toán bảo mật khác nhau, tính toán thống kê và thậm chí cả cơ sở dữ liệu lỗ hổng bảo mật (chứa các điểm yếu phổ biến và mã khai thác tương ứng) để xác định xem hệ thống có đang đối mặt với bất kỳ mối đe dọa, lỗ hổng hay rủi ro nào tại thời điểm đánh giá hay không (chẳng hạn như đăng nhập bất thường, các yêu cầu web lạ, phần mềm lỗi thời, v.v.). Sau đó, hệ thống báo cáo thông tin này cho bộ phận bảo mật của tổ chức thông qua các báo cáo, biểu đồ và thậm chí là cảnh báo qua SMS (trong trường hợp phát hiện lỗ hổng nghiêm trọng).

## Quy trình hoạt động của SEM

1.  **Thu thập (Collect):** Nhận nhật ký (logs) qua Syslog, truyền tệp, các tác nhân (agents) hoặc các phương tiện khác.
2.  **Chuẩn hóa (Normalise):** Chuẩn hóa thông tin nhật ký, ví dụ: đưa về định dạng ngày tháng và ký hiệu địa chỉ chung.
3.  **Làm phong phú (Enrich):** Bổ sung dữ liệu về mã khai thác đã biết công khai, kiểm kê tài sản của bạn, kết quả quét lỗ hổng bảo mật của riêng bạn.
4.  **Tương quan hóa (Correlate):** Nhóm, phân loại mức độ ưu tiên và gắn cờ các sự kiện, đồng thời loại bỏ các kết quả dương tính giả.
5.  **Báo cáo (Report):** Hiển thị sự kiện theo thời gian thực hoặc tạo báo cáo hoạt động định kỳ, gửi cảnh báo qua Email, SMS hoặc các phương tiện khác.

## Ưu điểm & Nhược điểm

Như có thể thấy, SEM là những dịch vụ mang lại nhiều lợi ích cho người dùng khi triển khai trong tổ chức của họ. Một số lợi ích bao gồm:
* Tập trung hóa thông tin từ các thiết bị và thành phần mạng khác nhau.
* Giảm thiểu các trường hợp dương tính giả (false positives) và âm tính giả (false negatives).
* Cải thiện đáng kể thời gian phản hồi đối với các mối đe dọa từ bên trong và bên ngoài.

Tuy nhiên, luôn cần nhắc đến một số nhược điểm có thể ảnh hưởng đến người dùng khi muốn triển khai loại giải pháp này cho mạng của họ:
* Chúng là những công cụ khó triển khai.
* Chúng có chi phí thị trường cao.
* Vì là hệ thống tự động, chúng có thể gặp lỗi dẫn đến việc xuất hiện các trường hợp dương tính giả và âm tính giả.

Các hệ thống bảo mật sẽ luôn đối mặt với rủi ro, vì vậy nhờ có những công cụ này, cuộc sống và công việc của các nhà phân tích cũng như đội ngũ bảo mật của tổ chức trở nên dễ dàng hơn. Dù vậy, cần nhớ rằng tự động hóa không phải là tất cả trong môi trường bảo mật: rốt cuộc, vấn đề không nằm ở việc ai phân tích hệ thống nhanh nhất, mà là ai có thể giữ cho hệ thống an toàn và hoạt động lâu nhất.

# Phân biệt SIM và SEM

Dựa vào chức năng và mục đích sử dụng trong hệ thống bảo mật, điểm khác biệt lớn nhất giữa SIM và SEM nằm ở **yếu tố thời gian** và **mục đích sử dụng chính**.

Dưới đây là bảng so sánh chi tiết:

| Tiêu chí | SIM (Security Information Management) | SEM (Security Event Management) |
| :--- | :--- | :--- |
| **Trọng tâm thời gian** | Dữ liệu lịch sử (Quá khứ / Dài hạn). | Thời gian thực (Hiện tại / Ngay lập tức). |
| **Mục đích chính** | Tập trung lưu trữ nhật ký (log), phân tích xu hướng, lập báo cáo và kiểm toán. | Phát hiện các mối đe dọa ngay khi nó vừa xảy ra, phân tích hành vi bất thường và phản hồi sự cố. |
| **Chức năng cốt lõi** | Quản lý log, dịch và chuẩn hóa log từ nhiều nguồn, lưu trữ khối lượng dữ liệu lớn. | Tương quan sự kiện (Correlation), giám sát liên tục, sử dụng thuật toán để đối chiếu với cơ sở dữ liệu lỗ hổng. |
| **Đầu ra (Output)** | Các bản báo cáo (Reports), biểu đồ, đồ thị thống kê tổng quan. | Các cảnh báo (Alerts), thông báo khẩn cấp qua SMS/Email, phản ứng chặn đứng tự động. |

### Tóm tắt

* **SIM** giống như một **kho lưu trữ hồ sơ**, nơi bạn cất giữ mọi bản ghi chép để sau này có thể tra cứu, kiểm tra xem hệ thống đã hoạt động ra sao trong quá khứ.
* **SEM** giống như một **hệ thống camera an ninh có chuông báo động**, liên tục giám sát ngay lúc này và sẽ réo lên ngay lập tức nếu phát hiện có kẻ đang cố gắng xâm nhập.

*Lưu ý: Trong thực tế hiện nay, hai công nghệ này thường không đứng riêng lẻ mà được gộp chung lại thành một hệ thống toàn diện gọi là **SIEM (Security Information and Event Management)**, kết hợp khả năng cảnh báo tức thời (SEM) và lưu trữ dữ liệu lịch sử để điều tra chuyên sâu (SIM).*

# SIEM LÀ GÌ?

Quản lý Sự kiện và Thông tin Bảo mật (SIEM - Security Information and Event Management) là một giải pháp phần mềm tổng hợp và phân tích hoạt động từ các tài nguyên khác nhau trên toàn bộ cơ sở hạ tầng CNTT của một tổ chức. 

SIEM là sự kết hợp giữa quản lý thông tin bảo mật (SIM) và quản lý sự kiện bảo mật (SEM), sử dụng các quy tắc (rules) và mối tương quan thống kê để giúp các tổ chức phát hiện các mối đe dọa và biến các mục nhật ký (log entries) cùng sự kiện từ các hệ thống bảo mật thành thông tin có thể hành động.

SIEM thu thập dữ liệu bảo mật từ các thiết bị mạng, máy chủ, bộ điều khiển miền (domain controllers) và nhiều nguồn khác. Sau đó, nó lưu trữ, chuẩn hóa, tổng hợp và áp dụng phân tích vào dữ liệu đó, giúp đội ngũ bảo mật phát hiện các mối đe dọa, quản lý ứng phó sự cố và thực hiện điều tra pháp y (forensic investigation).

Thiết lập các công cụ SIEM là một nhiệm vụ phức tạp ngay cả đối với chuyên gia bảo mật giỏi nhất, nhưng nếu thực hiện đúng, nó có thể loại bỏ các điểm mù trên toàn mạng. 
* Bước đầu tiên bao gồm việc hiểu mạng lưới và hệ thống bảo mật hiện tại của bạn, đồng thời tìm ra cách thu thập thông tin nhật ký từ những điểm đó. 
* Bạn cũng sẽ cần cân nhắc lập kế hoạch cho phần cứng nếu nhà cung cấp không đưa ra tùy chọn lưu trữ dưới dạng phần mềm dịch vụ (SaaS). 
* Cuối cùng, một bước diễn ra liên tục là viết các quy tắc để phát hiện các sự kiện đáng chú ý và tạo báo cáo nhằm làm nổi bật các số liệu chính về rủi ro mạng tổng thể.


Bên trên là sơ đồ đơn giản về kiến trúc SIEM. Các thiết bị khác nhau (Log Sources) sẽ được cấu hình để gửi nhật ký đến máy chủ Tương quan hóa (Correlation Engine Server) để phân tích, sau đó được lưu trữ trong Cơ sở dữ liệu (Database). Kết quả phân tích do máy chủ tương quan thực hiện sẽ được hiển thị trên Bảng điều khiển (SIEM Dashboard) giao diện người dùng, nơi các nhà phân tích bảo mật truy cập để xác định, phân loại và phản hồi các sự kiện bảo mật.

## LỢI ÍCH CỦA SIEM

* **Phát hiện Mối đe dọa Nâng cao:** Phần mềm độc hại đã tiến hóa theo cách trốn tránh được sự phát hiện của các giải pháp diệt virus truyền thống, tường lửa, hệ thống phát hiện/ngăn ngừa xâm nhập và các giải pháp bảo mật khác. Nhiều tổ chức đã triển khai chiến lược phòng thủ chiều sâu, từ đó tạo ra một lượng dữ liệu khổng lồ rất khó giám sát. Vì vậy, giải pháp phát hiện mối đe dọa nâng cao đã ra đời. SIEM có khả năng giám sát và tương quan hóa liên tục theo thời gian thực trên toàn bộ quy mô của doanh nghiệp, giúp phát hiện, giảm nhẹ và ngăn chặn các mối đe dọa nâng cao như kẻ gian nội bộ và rò rỉ dữ liệu.
* **Điều tra Pháp y và Phản hồi Sự cố:** Quá trình điều tra pháp y có thể kéo dài vì nhà phân tích phải diễn giải dữ liệu nhật ký để xác định chuyện gì đã xảy ra, đồng thời bảo quản dữ liệu để nó có giá trị trước pháp luật. SIEM giúp tổ chức điều tra bằng cách lưu trữ/bảo vệ nhật ký lịch sử và cung cấp các công cụ để điều hướng, tương quan dữ liệu nhanh chóng. Nhờ đó, nhà phân tích bảo mật sớm nhận ra sự cố đang diễn ra và thiết lập các bước khắc phục ngay lập tức.
* **Báo cáo Tuân thủ và Kiểm toán:** Về cơ bản, SIEM được triển khai để đáp ứng các yêu cầu tuân thủ của chính phủ. Mọi doanh nghiệp đều bị ràng buộc bởi các quy định như HIPAA, PCI/DSS, SOX, FERPA và HITECH. SIEM giúp các tổ chức chứng minh cho kiểm toán viên và cơ quan quản lý thấy rằng các yêu cầu đang được đáp ứng bằng cách tổng hợp dữ liệu nhật ký và trình bày nó ở định dạng sẵn sàng cho kiểm toán.
* **Các lý do khác:** Doanh nghiệp cũng cần SIEM cho việc lưu trữ dữ liệu, đạt được và duy trì các chứng chỉ (như ISO 27000, ISO 27001, 27002, 27003), quản lý và lưu giữ nhật ký, hệ thống quản lý ca vụ (ticketing), cũng như xác thực việc thực thi và vi phạm chính sách.
# CÁC NỀN TẢNG SIEM (SIEM PLATFORMS)

Bài học này được thiết kế để cung cấp cho bạn cái nhìn sâu sắc về các nền tảng SIEM khác nhau trên thị trường. Chúng ta sẽ khám phá các nền tảng, cùng với khả năng, điểm mạnh và điểm yếu của chúng. Chúng ta cũng sẽ giới thiệu với bạn về nền tảng mà chúng ta sẽ sử dụng trong khóa học này để rèn luyện các kỹ năng SIEM: Splunk.

## GRAYLOG
*(https://www.graylog.org/)*

Graylog cung cấp hai sản phẩm SIEM khác nhau: Graylog Open Source (mã nguồn mở, miễn phí 100%) và sản phẩm trả phí Graylog Enterprise. Nếu bạn muốn tải xuống và thử nghiệm với Graylog Open Source, bạn có thể tải về trực tiếp từ trang web. Graylog Enterprise có giới hạn sử dụng miễn phí và có thể được dùng bởi các tổ chức nhỏ với mức xử lý ít hơn 5 GB sự kiện mỗi ngày.

## ARCSIGHT
*(https://www.microfocus.com/en-us/products/siem-security-information-event-management/overview)*

ArcSight (với sản phẩm SIEM ArchSight, còn được gọi là ArcSight Enterprise Security Management, hay ESM) tuyên bố rằng nó có thể giúp các Trung tâm Điều hành An ninh (SOC) xây dựng phương pháp tiếp cận phân tích phân lớp bằng cách tích hợp với nhiều công cụ bảo mật thương mại. Nó cũng cung cấp các quy trình làm việc Tự động hóa và Phản hồi Bảo mật (SOAR) để tự động hóa việc phản hồi đối với các sự kiện bảo mật, giúp các nhà phân tích có thể tập trung vào các cuộc điều tra quan trọng hơn. Khả năng tương quan hóa theo thời gian thực mạnh mẽ trong ArcSight được khẳng định là cách nhanh nhất để phát hiện các mối đe dọa từ các tập dữ liệu lớn.

## QRADAR
*(https://www.ibm.com/uk-en/security/security-intelligence/qradar)*

Ngoài các khả năng cơ bản của SIEM, QRadar SIEM cũng cung cấp khả năng nhập dữ liệu từ các nguồn cấp dữ liệu tình báo mối đe dọa (threat intelligence feeds). Khi mua QRadar, khách hàng cũng có thể chọn đăng ký dịch vụ IBM Security X-Force Threat Intelligence trả phí, giúp xác định các chỉ báo độc hại để làm phong phú thêm quá trình điều tra hoặc tạo cảnh báo ngay lập tức. QRadar còn có các mô-đun bổ sung hỗ trợ các nhóm bảo mật trong việc phản hồi sự cố, quản lý rủi ro và quản lý lỗ hổng bảo mật.

## LOGRHYTHM
*(https://logrhythm.com)*

LogRhythm tự hào có một số tính năng khá ấn tượng, chẳng hạn như học máy (machine learning), Tự động hóa và Phản hồi Bảo mật (SOAR), Phân tích Hành vi Người dùng Cuối (UEBA) và Phát hiện & Phản hồi Mạng (NDR) để mang lại khả năng hiển thị môi trường và khả năng phản hồi vượt trội trực tiếp từ nền tảng SIEM. LogRhythm cũng cho biết bạn sẽ dễ dàng thiết lập đường cơ sở (baseline) cho chương trình vận hành bảo mật của mình và theo dõi các thành quả đạt được, nhờ đó bạn có thể dễ dàng báo cáo những thành công của mình cho ban giám đốc.

## SPLUNK
*(https://www.splunk.com/en_us/platform.html)*

Splunk là một trong những nền tảng SIEM phổ biến nhất trong ngành. Các quản trị viên SIEM có thể tải xuống và thêm các "Ứng dụng" (Apps) cung cấp chức năng bổ sung cho Splunk, chẳng hạn như phân tích, bảng điều khiển (dashboards), cải thiện tìm kiếm và thao tác dữ liệu. Dữ liệu đã nhập có thể được tìm kiếm bằng các truy vấn (search queries) tùy chỉnh, và các truy vấn này cũng có thể được sử dụng để tạo cảnh báo hoặc tạo các bảng điều khiển trực quan.
