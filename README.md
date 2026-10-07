# Day 21 — Phân tích rủi ro AI trong y tế

## Thông tin học viên

- **Họ và tên:** Bùi Thị Ngọc Trân
- **MSSV / mã học viên:** 2A202602529
- **Lớp:** Track1-H201
- **Ngành đã chọn:** Y tế.
- **Phạm vi:** Trợ lý sức khỏe và công cụ đánh giá triệu chứng (health assistant / symptom checker).

## 1. Industry Risk Snapshot

| Nội dung | Đánh giá và căn cứ |
| --- | --- |
| **Tác hại chính có thể xảy ra** | Khuyến nghị không phù hợp có thể khiến người dùng tự chăm sóc sai, trì hoãn khám hoặc bỏ lỡ cấp cứu. Nội dung thiếu nhạy cảm với bối cảnh sức khỏe tâm thần có thể củng cố hành vi nguy hiểm. Ngoài ra, việc xử lý dữ liệu sức khỏe tạo nguy cơ mất riêng tư; kết quả thiếu công bằng có thể khiến một số nhóm nhận hỗ trợ kém hơn. |
| **Mức độ high-stakes** | **Cao — đánh giá định tính của bài.** AI tham gia quyết định liên quan đến sức khỏe và thời điểm tìm kiếm chăm sóc. Sai sót có thể gây tổn hại thể chất nghiêm trọng, đặc biệt khi bỏ sót tình huống cấp cứu. |
| **Dữ liệu nhạy cảm có thể được sử dụng** | Triệu chứng, bệnh sử, thuốc đang dùng, kết quả xét nghiệm, tuổi, tình trạng mang thai và thông tin sức khỏe tâm thần. Khi gắn với danh tính hoặc lịch sử hội thoại, dữ liệu này có thể tiết lộ tình trạng sức khỏe cá nhân. |
| **Nhu cầu human review** | **Cao — đánh giá định tính của bài.** Cần có cơ chế chuyển tới chuyên gia khi xuất hiện dấu hiệu nguy hiểm, người dùng dễ tổn thương hoặc thông tin chưa đủ để đưa ra khuyến nghị. Quyết định chẩn đoán và điều trị cần được chuyên gia y tế đánh giá phù hợp với bối cảnh. |

Các mức đánh giá trong bài phục vụ phân tích rủi ro của bài tập, không phải kết luận phân loại pháp lý. Hai case dưới đây khác nhau: một sự kiện chatbot đưa lời khuyên không phù hợp và một nghiên cứu đánh giá khuyến nghị của symptom checker.

## 2. Case 1 — NEDA Tessa: lời khuyên giảm cân trong bối cảnh rối loạn ăn uống

### 2.1. Brief Case

| Nội dung | Thông tin |
| --- | --- |
| **Tổ chức / sản phẩm** | National Eating Disorders Association (NEDA); chatbot Tessa do Cass vận hành. |
| **Thời gian / bối cảnh** | Hoa Kỳ, tháng 5/2023; bài tường thuật của Kate Wells được KFF Health News đăng ngày 12/6/2023. |
| **AI được dùng để làm gì?** | Hỗ trợ chương trình về hình ảnh cơ thể. Thiết kế ban đầu dùng kịch bản; nhà cung cấp cho biết đã bổ sung hỏi–đáp dùng generative AI. |
| **Vấn đề được ghi nhận** | Người thử nghiệm nhận lời khuyên giảm cân không phù hợp với bối cảnh rối loạn ăn uống. NEDA thông báo dừng Tessa ngày 30/5/2023. |
| **Số liệu liên quan** | Trong tương tác được bài báo tường thuật, chatbot khuyên giảm **1–2 pound/tuần** và tạo mức thâm hụt **500–1.000 calorie/ngày**. Đây là nội dung khuyến nghị được báo cáo, không phải tỷ lệ lỗi hoặc số người bị tổn hại. |
| **Nguồn** | [S1 — Kate Wells, KFF Health News](https://kffhealthnews.org/mental-health/what-does-a-chatbot-know-about-eating-disorders-users-of-a-help-line-are-about-to-find-out/), bài thuộc hợp tác Michigan Radio, NPR và KFF Health News. |

**Bằng chứng và giới hạn:** S1 ghi nhận lời khuyên và việc dừng chatbot; chưa xác nhận tổn hại sức khỏe cụ thể do lời khuyên này. NEDA và Cass bất đồng về việc thay đổi tính năng có được chấp thuận hay không. Không thể từ bài báo xác định chính xác kiến trúc hoặc nguyên nhân kỹ thuật gốc.

### 2.2. Harm Map — đủ 11 trường

**Luồng phân tích:** Người dễ tổn thương nhận hướng dẫn giảm cân → Harmful advice → Chưa xác định layer, giả thuyết Safety → Nguy cơ củng cố hành vi nguy hiểm → High.

| Trường | Phân tích |
| --- | --- |
| **1. High-risk moment** | Khi người có rối loạn ăn uống hoặc nguy cơ mắc bệnh tìm hỗ trợ từ Tessa và nhận hướng dẫn cụ thể về giảm cân, calorie hoặc hạn chế ăn. |
| **2. Stakeholder bị ảnh hưởng** | Người dùng trực tiếp, người thân, chuyên gia điều trị và đơn vị vận hành NEDA/Cass. Người dùng chịu nguy cơ sức khỏe; người thân và chuyên gia có thể phải hỗ trợ nếu tình trạng xấu đi; đơn vị vận hành chịu ảnh hưởng về niềm tin. |
| **3. Failure mode** | **Harmful advice** là mode chính: lời khuyên có thể thúc đẩy hành vi nguy hiểm trong bối cảnh người dùng dễ tổn thương. Không đủ bằng chứng để xác định lỗi escalation trong tương tác này, vì chưa rõ tiêu chí chuyển người thật đã được thiết kế ra sao. |
| **4. Layer bắt đầu lỗi** | **Chưa đủ bằng chứng để xác định. Giả thuyết: Safety.** Đầu ra cho thấy giới hạn nội dung chưa ngăn được lời khuyên không phù hợp. Đây là suy luận về chức năng bảo vệ cần có, không chứng minh lỗi bắt đầu ở một guardrail cụ thể. Grounding hoặc Model cũng chưa được loại trừ. |
| **5. Harm xảy ra là gì?** | **Người có rối loạn ăn uống có nguy cơ bị củng cố hành vi hạn chế ăn và ám ảnh cân nặng khi họ làm theo lời khuyên giảm cân của chatbot.** Tác hại sức khỏe này là nguy cơ phân tích, chưa được nguồn xác nhận đã xảy ra. |
| **6. Harm lens** | **Injury:** nguy cơ tổn hại sức khỏe do hành vi ăn uống nguy hiểm. Không tự gán misinformation chỉ vì lời khuyên không phù hợp với người nhận; không cần chứng minh nội dung bịa đặt để xác định harmful advice. |
| **7. Severity** | **High — nhận định của bài về hậu quả tiềm tàng.** Hành vi hạn chế ăn có thể làm tình trạng người dễ tổn thương xấu đi. Mức độ thực tế phụ thuộc bệnh trạng và việc làm theo lời khuyên; bài không xác nhận hậu quả đã xảy ra. |
| **8. Scale** | **Chưa đủ dữ liệu để đánh giá.** Phần mềm có thể phục vụ nhiều người, nhưng chưa có số người thực tế nhận lời khuyên tương tự. Khả năng mở rộng không tương đương quy mô tác hại đã ghi nhận. |
| **9. Probability** | **Chưa đủ dữ liệu để đánh giá.** Tương tác được báo cáo chứng minh lỗi có thể xảy ra, nhưng thiếu mẫu đại diện và tổng số lượt sử dụng để ước lượng xác suất lỗi hoặc tổn hại. |
| **10. Frequency** | **Chưa đủ dữ liệu để đánh giá.** S1 cho thấy có phản hồi không phù hợp được báo cáo; chưa có thống kê theo thời gian để xác định lỗi lặp lại thường xuyên đến đâu. |
| **11. Vì sao?** | Nhóm người dùng và thời điểm tiếp nhận lời khuyên làm nguy cơ sức khỏe đáng quan tâm. S1 hỗ trợ việc nhận diện harmful advice, nhưng chưa đủ để định lượng quy mô, xác suất, tần suất hoặc xác định layer. Severity được đánh giá theo hậu quả có thể xảy ra, không dựa trên số người đã bị hại. |

## 3. Case 2 — Nghiên cứu đánh giá symptom checker và khuyến nghị triage

### 3.1. Brief Case

| Nội dung | Thông tin |
| --- | --- |
| **Nghiên cứu / sản phẩm** | Gilbert và cộng sự, BMJ Open: Ada, Babylon, Buoy, K Health, Mediktor, Symptomate, WebMD và Your.MD. |
| **Thời gian / bối cảnh** | Công bố **16/12/2020**; so sánh **8 ứng dụng** và **7 bác sĩ đa khoa (GP)** trên **200 tình huống lâm sàng mô phỏng (clinical vignettes)**. |
| **AI được dùng để làm gì?** | Thu thập triệu chứng, gợi ý bệnh và khuyến nghị mức độ khẩn cấp của việc tìm chăm sóc (**triage**). Không giả định tất cả ứng dụng đều dùng LLM hoặc cùng kiến trúc. |
| **Vấn đề được ghi nhận** | Hiệu năng khác nhau giữa ứng dụng; một số khuyến nghị không đạt tiêu chí “safe urgency advice” của nghiên cứu. |
| **Số liệu liên quan** | Tỷ lệ safe urgency advice: **GP trung bình 97,0%; Buoy 80,0%; K Health 81,3%; Mediktor 87,3%**. Tỷ lệ ứng dụng tính trên các vignette **có cung cấp khuyến nghị**, không mặc định trên toàn bộ 200 ca. |
| **Nguồn** | [S2 — PubMed](https://pubmed.ncbi.nlm.nih.gov/33328258/) và [S3 — bài BMJ Open](https://doi.org/10.1136/bmjopen-2020-040269). |

**Cách hiểu số liệu:** “Safe” bao gồm khuyến nghị bằng mức chuẩn, thận trọng hơn hoặc thấp hơn tối đa một mức. Vì vậy safe urgency advice không đồng nghĩa với triage chính xác hoàn toàn, cũng không đo tỷ lệ bệnh nhân tránh được tổn hại.

**Giới hạn:** Đây là kết quả thử nghiệm năm 2020, không đại diện phiên bản hiện tại hay hậu quả trên bệnh nhân thật. Phần lớn tác giả công bố quan hệ việc làm, tư vấn hoặc sở hữu với Ada Health; cần lưu ý xung đột lợi ích khi diễn giải.

### 3.2. Harm Map — đủ 11 trường

**Luồng phân tích:** Người cần cấp cứu nhận khuyến nghị chăm sóc thấp → Harmful advice → Chưa đủ bằng chứng về layer → Nguy cơ trì hoãn cấp cứu → Critical.

| Trường | Phân tích |
| --- | --- |
| **1. High-risk moment** | Khi một người thực sự cần chăm sóc khẩn cấp sử dụng symptom checker để quyết định có đi cấp cứu hay không, nhưng ứng dụng khuyến nghị mức chăm sóc thấp hơn cần thiết. Đây là tình huống rủi ro chọn để phân tích, không phải ca bệnh thật được nghiên cứu theo dõi. |
| **2. Stakeholder bị ảnh hưởng** | Bệnh nhân, người thân, bác sĩ và cơ sở y tế. Bệnh nhân chịu nguy cơ chậm chăm sóc; người thân có thể phải xử lý tình trạng xấu đi; nhân viên y tế có thể tiếp nhận ca bệnh muộn hơn. |
| **3. Failure mode** | **Harmful advice:** khuyến nghị chăm sóc không an toàn. **Over-reliance** là yếu tố có thể khuếch đại tác hại nếu người dùng tin hoàn toàn vào kết quả, nhưng nghiên cứu không đo hành vi phụ thuộc này. Chẩn đoán sai không tự động là hallucination. |
| **4. Layer bắt đầu lỗi** | **Chưa đủ bằng chứng để xác định.** Đánh giá đầu ra không chỉ ra lỗi bắt đầu ở UX, Grounding, Safety hay Model. **Giả thuyết:** khả năng nhận diện dấu hiệu nguy hiểm hoặc quy tắc phân luồng có thể chưa phù hợp; cần dữ liệu về thiết kế và log để kiểm tra. |
| **5. Harm xảy ra là gì?** | **Bệnh nhân có nguy cơ bị chậm cấp cứu và tổn hại thể chất khi làm theo khuyến nghị triage thấp hơn mức cần thiết.** Nghiên cứu ghi nhận khuyến nghị không đạt tiêu chí an toàn, không chứng minh tổn hại trên bệnh nhân thật. |
| **6. Harm lens** | **Injury** là lens chính: nguy cơ bệnh tiến triển hoặc tổn hại thể chất do trì hoãn chăm sóc. **Misinformation** là lens bổ sung nếu đánh giá sai mức độ khẩn cấp khiến người dùng hiểu sai tình trạng. |
| **7. Severity** | **Critical — nhận định về tình huống cấp cứu đã chọn.** Chậm cấp cứu có thể dẫn đến hậu quả thể chất đặc biệt nghiêm trọng. Không gán Critical cho mọi lỗi triage hoặc mọi ứng dụng trong nghiên cứu. |
| **8. Scale** | **Phạm vi thử nghiệm: 200 vignette, 8 ứng dụng và 7 GP. Quy mô tác hại ngoài thực tế: chưa đủ dữ liệu.** Số vignette không phải số bệnh nhân bị ảnh hưởng. |
| **9. Probability** | **Xác suất tổn hại ngoài thực tế: chưa đủ dữ liệu.** Tỷ lệ safe urgency advice ở Brief Case phản ánh đầu ra trên tập thử nghiệm. Không chuyển phần còn lại thành phần trăm bệnh nhân bị hại; tổn hại còn phụ thuộc loại bệnh, hành vi người dùng và hỗ trợ khác. |
| **10. Frequency** | **Chưa đủ dữ liệu để đánh giá tần suất ngoài thực tế.** Có lỗi trong tập thử nghiệm, nhưng nghiên cứu không đo số lỗi mỗi ngày/tháng hoặc theo hành vi sử dụng thực của người bệnh. |
| **11. Vì sao?** | Mức triage ảnh hưởng thời điểm tìm chăm sóc nên hậu quả có thể nghiêm trọng trong ca cấp cứu. S2/S3 cung cấp bằng chứng về hiệu năng thử nghiệm, không xác nhận tác hại thực tế, nguyên nhân kỹ thuật hay tần suất vận hành. Cần giữ riêng mức độ nghiêm trọng của kịch bản và khả năng kịch bản xảy ra. |

## 4. Bài học rút ra

- **An toàn cần gắn với nhóm người dùng:** khuyến nghị có vẻ thông thường có thể gây hại trong bối cảnh rối loạn ăn uống.
- **Đánh giá đầu ra chưa đủ xác định nguyên nhân:** muốn kết luận layer phải có bằng chứng về thiết kế, dữ liệu hoặc quá trình vận hành.
- **Đọc rõ định nghĩa metric và mẫu số:** “safe”, “đúng” và “không gây tổn hại” là các khái niệm khác nhau.
- **Tách lỗi đã quan sát và tác hại suy luận:** chỉ khẳng định tổn hại đã xảy ra khi nguồn có bằng chứng tương ứng.
- **Severity không quyết định Probability/Frequency:** kịch bản có hậu quả nghiêm trọng vẫn có thể thiếu dữ liệu về xác suất và tần suất.

## 5. Nguồn tham khảo

1. **S1 — Kate Wells, KFF Health News, 12/6/2023.** *What Does a Chatbot Know About Eating Disorders? Users of a Help Line Are About to Find Out.* [Đọc bài](https://kffhealthnews.org/mental-health/what-does-a-chatbot-know-about-eating-disorders-users-of-a-help-line-are-about-to-find-out/). Dùng cho tương tác Tessa và việc dừng chatbot.
2. **S2 — Gilbert và cộng sự, PubMed, 16/12/2020.** *How accurate are digital symptom assessment apps for suggesting conditions and urgency advice? A clinical vignettes comparison to GPs.* [Đọc tóm tắt và công bố lợi ích](https://pubmed.ncbi.nlm.nih.gov/33328258/). Dùng cho thiết kế, số liệu và định nghĩa safe urgency advice.
3. **S3 — BMJ Open, 2020;10:e040269.** [DOI: 10.1136/bmjopen-2020-040269](https://doi.org/10.1136/bmjopen-2020-040269); [bản toàn văn PMC](https://pmc.ncbi.nlm.nih.gov/articles/PMC7745523/). S2 và S3 là cùng một nghiên cứu, không tính thành hai case.
