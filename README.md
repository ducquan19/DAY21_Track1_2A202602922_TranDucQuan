# Lab 21 - Phân tích rủi ro AI qua case study thực tế

- Họ và tên: Trần Đức Quân
- MSSV / mã học viên: 2A202602922
- Lớp: Track 1
- Ngành đã chọn: HR / tuyển dụng

---

### 1. Industry Risk Snapshot

| Nội dung | Đánh giá của tôi và lý do |
| --- | --- |
| Những tác hại chính có thể xảy ra | Phân biệt đối xử/bất bình đẳng tuyển dụng (bias về giới tính, độ tuổi, chủng tộc); mất cơ hội việc làm và thu nhập đối với các ứng viên yếu thế; suy giảm phẩm giá ứng viên khi bị đánh giá phiến diện qua video/biểu cảm. |
| Mức độ high-stakes | **Cao**. Việc làm quyết định sinh kế, phúc lợi, bảo hiểm y tế và sự phát triển sự nghiệp của cá nhân. Quyết định loại hồ sơ sai ở quy mô tự động hóa sẽ tước đoạt cơ hội sống của hàng loạt người. |
| Dữ liệu nhạy cảm có thể được sử dụng | Thông tin cá nhân, giới tính, ngày sinh, địa chỉ cư trú, trường học, hình ảnh chân dung, giọng nói/video phỏng vấn, lịch sử việc làm và mức lương cũ. |
| Nhu cầu human review | **Cao**. Cần chuyên viên tuyển dụng (HR Recruiter/Talent Acquisition) kiểm tra và rà soát ở giai đoạn lọc hồ sơ và phỏng vấn sơ loại; AI chỉ nên đóng vai trò hỗ trợ tóm tắt/gợi ý thay vì tự động ra quyết định loại bỏ ứng viên (Human-in-the-loop). |

---

### 2. Case study 1 - Hệ thống AI lọc hồ sơ tuyển dụng tự động của Amazon

#### Brief Case

- Tổ chức / sản phẩm AI: Amazon (Hệ thống AI sàng lọc hồ sơ CV nội bộ).
- Thời gian, địa điểm / bối cảnh: Triển khai thử nghiệm từ năm 2014 đến 2018 tại Edinburgh, Scotland và Seattle, Mỹ nhằm tự động chấm điểm ứng viên từ 1 đến 5 sao.
- AI được dùng để làm gì: Tự động quét và chấm điểm hồ sơ xin việc để chọn ra top ứng viên phù hợp nhất cho các vị trí kỹ sư phần mềm.
- Vấn đề hoặc sự kiện đáng chú ý: Hệ thống tự động học thiên vị giới tính, phạt điểm các hồ sơ có chứa từ khóa liên quan đến phụ nữ (ví dụ: "women's chess club captain") hoặc các trường đại học nữ sinh.
- Số liệu có nguồn: Mô hình được huấn luyện trên tập dữ liệu gồm các CV nộp vào Amazon trong khoảng thời gian **10 năm** (phần lớn do nam giới chiếm ưu thế do đặc thù ngành tech); năm 2015 nhóm kỹ thuật phát hiện hệ thống đã phạt điểm các ứng viên chứa từ khóa "women's" và đánh giá thấp sinh viên tốt nghiệp từ **2 trường cao đẳng dành riêng cho nữ giới** (theo điều tra độc quyền của Reuters, công bố tháng 10/2018).
- Nguồn: Reuters - Jeffrey Dastin - 10/10/2018 - "Amazon scraps secret AI recruiting tool that showed bias against women" (Reuters Technology News). [Link](https://www.reuters.com/article/world/insight-amazon-scraps-secret-ai-recruiting-tool-that-showed-bias-against-women-idUSKCN1MK0AG/)
- Phân biệt bằng chứng và nhận định:
  - *Bằng chứng:* Reuters xác nhận Amazon đã giải tán dự án vào năm 2018 sau khi không thể khắc phục triệt để bias; tập dữ liệu huấn luyện lịch sử 10 năm phản ánh thực trạng áp đảo của nam giới trong ngành công nghệ.
  - *Nhận định:* Dù Amazon khẳng định công cụ chưa từng được dùng độc lập để đưa ra quyết định tuyển dụng chính thức cuối cùng, nguy cơ các ứng viên nữ bị loại ngầm trong giai đoạn thử nghiệm nội bộ là hoàn toàn hiện hữu.

#### Harm Map Worksheet

| Trường | Phân tích của tôi |
| --- | --- |
| High-risk moment | Thời điểm mô hình AI chấm điểm (ranking) hồ sơ ứng viên và đưa ra danh sách đề xuất phỏng vấn cho nhà tuyển dụng. |
| Stakeholder bị ảnh hưởng | Ứng viên nữ nộp hồ sơ vào Amazon; nhóm tuyển dụng nội bộ Amazon; uy tín của tập đoàn Amazon. |
| Failure mode | Bias / fairness (thiên kiến hệ thống học từ dữ liệu lịch sử lệch lạc). |
| Layer bắt đầu lỗi | Grounding & Model (Dữ liệu đầu vào phản ánh sự mất cân bằng giới tính trong quá khứ; mô hình học tương quan giả tạo giữa giới tính nam và năng lực kỹ thuật). |
| Harm xảy ra là gì? | Nguy cơ mất cơ hội việc làm và thu nhập đối với các kỹ sư nữ; tổn hại uy tín thương hiệu của Amazon đã xảy ra sau phóng sự điều tra. |
| Harm lens | Mất cơ hội và tổn hại phẩm giá do bị phân biệt đối xử. |
| Severity | High (ảnh hưởng trực tiếp đến quyền tiếp cận việc làm và sinh kế của ứng viên). |
| Scale | Medium (công cụ chỉ được áp dụng thử nghiệm nội bộ với hàng nghìn hồ sơ tuyển dụng kỹ thuật tại Amazon, chưa bán thương mại ra ngoài). |
| Probability | High (khả năng mô hình gạt bỏ hồ sơ nữ là có hệ thống, được nhóm kỹ thuật ghi nhận lặp lại liên tục trong mã nguồn). |
| Frequency | High (xảy ra mỗi lần hệ thống quét các CV có chứa các đặc điểm/từ khóa liên quan đến nữ giới). |
| Vì sao? | Do mô hình machine learning tối ưu hóa việc tìm kiếm các đặc điểm tương đồng với nhân sự thành công trong quá khứ, biến thiên kiến xã hội thành quy tắc sàng lọc tự động mà thiếu cơ chế Safety/Fairness constraints. |

---

### 3. Case study 2 - Nền tảng phân tích video phỏng vấn HireVue loại bỏ tính năng Facial Analysis

#### Brief Case

- Tổ chức / sản phẩm AI: HireVue (Nền tảng phỏng vấn video ứng viên bằng AI).
- Thời gian, địa điểm / bối cảnh: Giai đoạn 2019–2021 tại Mỹ và toàn cầu; phục vụ hàng trăm tập đoàn lớn (như Unilever, Hilton).
- AI được dùng để làm gì: Phân tích biểu cảm khuôn mặt, chuyển động cơ mặt, giọng nói và từ ngữ của ứng viên qua video để dự đoán mức độ phù hợp với công việc và tính cách.
- Vấn đề hoặc sự kiện đáng chú ý: Bị EPIC (Electronic Privacy Information Center) đệ đơn khiếu nại lên FTC vào tháng 11/2019 vì quảng bá công nghệ ngụy khoa học, thiếu minh bạch và có nguy cơ phân biệt đối xử với người khuyết tật, người có biểu cảm khác biệt văn hóa.
- Số liệu có nguồn: HireVue đã thực hiện hơn **12 triệu cuộc phỏng vấn** cho hơn **700 doanh nghiệp** trước khi tuyên bố chính thức ngừng sử dụng tính năng phân tích biểu cảm khuôn mặt vào đầu năm 2021 sau một đợt kiểm toán độc lập của O’Neil Risk Consulting & Algorithmic Auditing (ORCAA) hoàn thành cuối năm 2020.
- Nguồn: [Link](https://epic.org/documents/in-re-hirevue/)
- Phân biệt bằng chứng và nhận định:
  - *Bằng chứng:* EPIC đã nộp đơn chính thức lên FTC; HireVue đã chính thức gỡ bỏ tính năng chấm điểm khuôn mặt từ đầu năm 2021 sau áp lực pháp lý và báo cáo audit.
  - *Nhận định:* Nhận định rằng tính năng phân tích cơ mặt là "khoa học giả" dựa trên sự đồng thuận của nhiều nhà khoa học dữ liệu, tuy nhiên chưa có phán quyết phạt hành chính chính thức từ FTC đối với HireVue.

#### Harm Map Worksheet

| Trường | Phân tích của tôi |
| --- | --- |
| High-risk moment | Thời điểm AI phân tích cử chỉ/biểu cảm khuôn mặt qua camera và tự động cho điểm tính cách/năng lực của ứng viên. |
| Stakeholder bị ảnh hưởng | Ứng viên xin việc (đặc biệt là người khuyết tật về cơ mặt, người tự kỷ, người thuộc nhóm thiểu số); doanh nghiệp sử dụng giải pháp (Unilever, Hilton); HireVue. |
| Failure mode | Bias / fairness & Over-reliance (hệ thống suy diễn sai lệch từ ngoại hình/biểu cảm sang năng lực; nhà tuyển dụng quá ỷ lại vào điểm số tự động). |
| Layer bắt đầu lỗi | Grounding & Model (Sử dụng giả thuyết khoa học chưa được kiểm chứng rằng co cơ mặt vi mô phản ánh đạo đức/năng lực làm việc; mô hình học từ dữ liệu thiếu đa dạng về thể chất thần kinh). |
| Harm xảy ra là gì? | Ứng viên bị tước cơ hội việc làm vô căn cứ và cảm thấy bị xúc phạm, phân loại bất công dựa trên đặc điểm cơ thể - đã diễn ra trên hàng ngàn ứng viên thực tế. |
| Harm lens | Mất cơ hội và tổn hại phẩm giá. |
| Severity | High (quyết định tự động làm mất cơ hội nghề nghiệp mà ứng viên không có cách nào giải trình hoặc khiếu nại). |
| Scale | High (hệ thống đã phỏng vấn hàng triệu ứng viên trên phạm vi toàn cầu của hơn 700 khách hàng doanh nghiệp). |
| Probability | Medium (không phải mọi ứng viên đều bị ảnh hưởng, nhưng xác suất bị chấm điểm bất lợi tăng vọt ở nhóm ứng viên có biểu cảm phi điển hình). |
| Frequency | High (diễn ra tự động trong suốt quá trình tính năng được bật trên mọi video phỏng vấn). |
| Vì sao? | Đánh giá dựa trên khiếu nại của tổ chức quyền riêng tư EPIC và kết quả rà soát của ORCAA, cho thấy tương quan giữa chuyển động cơ mặt và năng lực làm việc là không có cơ sở khoa học vững chắc, dẫn đến rủi ro thiên vị mang tính hệ thống. |

---

### 4. Case study 3 - Hệ thống gia sư trực tuyến iTutorGroup phân biệt tuổi tác ứng viên

#### Brief Case

- Tổ chức / sản phẩm AI: iTutorGroup (tập đoàn công nghệ giáo dục trực tuyến thuộc Ping An Insurance, cung cấp dịch vụ dạy tiếng Anh trực tuyến).
- Thời gian, địa điểm / bối cảnh: Giai đoạn 2020–2023 tại Mỹ; vụ việc do Ủy ban Cơ hội Việc làm Bình đẳng Hoa Kỳ (EEOC) thụ lý.
- AI được dùng để làm gì: Tự động tiếp nhận, phân loại và sàng lọc ban đầu hàng ngàn hồ sơ ứng tuyển vị trí gia sư trực tuyến thông qua phần mềm tuyển dụng tự động.
- Vấn đề hoặc sự kiện đáng chú ý: Thuật toán tuyển dụng tự động được cài đặt để tự động từ chối ứng viên dựa trên độ tuổi (ứng viên nữ từ 55 tuổi trở lên và ứng viên nam từ 60 tuổi trở lên), vi phạm nghiêm trọng Đạo luật Chống phân biệt tuổi tác trong việc làm (ADEA).
- Số liệu có nguồn: Hệ thống đã tự động gạt bỏ hơn **200 ứng viên đủ điều kiện** chỉ vì năm sinh; vào tháng 8/2023, iTutorGroup đồng ý chi trả **365.000 USD** để bồi thường cho các ứng viên bị ảnh hưởng và chấp thuận sự giám sát chống phân biệt đối xử của tòa án trong 5 năm (theo thông cáo giải quyết vụ kiện chính thức của EEOC).
- Nguồn: Thomson Reuters - Thomson Reuters Legal Blog - 22/09/2023 - [Link](https://tax.thomsonreuters.com/blog/legal-expert-employers-should-conduct-regular-auditing-of-a-i-tools-used-for-employment-practices/)
- Phân biệt bằng chứng và nhận định:
  - *Bằng chứng:* Thông cáo pháp lý và thỏa thuận hòa giải (consent decree) của EEOC xác nhận phần mềm tuyển dụng của công ty bị cài quy tắc/tham số tự động loại bỏ ứng viên lớn tuổi; số tiền phạt và số ứng viên bị ảnh hưởng được tòa án ghi nhận.
  - *Nhận định:* Dù iTutorGroup phủ nhận hành vi cố ý vi phạm trong quá trình dàn xếp, việc thuật toán tích hợp logic loại bỏ cứng theo độ tuổi cho thấy sự tắc trách nghiêm trọng trong quy trình thiết kế và kiểm thử an toàn (safety/fairness audit) trước khi vận hành.

#### Harm Map Worksheet

| Trường | Phân tích của tôi |
| --- | --- |
| High-risk moment | Thời điểm ứng viên điền ngày sinh/năm sinh vào biểu mẫu và hệ thống phần mềm chạy thuật toán sàng lọc để quyết định gửi email từ chối hay chuyển tiếp vòng trong. |
| Stakeholder bị ảnh hưởng | Ứng viên gia sư lớn tuổi (nữ từ 55+, nam từ 60+); học viên iTutorGroup (mất cơ hội học với giáo viên giàu kinh nghiệm); iTutorGroup (chịu phạt tài chính và khủng hoảng uy tín). |
| Failure mode | Bias / fairness (phân biệt đối xử trực tiếp và có hệ thống theo độ tuổi - Age discrimination). |
| Layer bắt đầu lỗi | Safety & Grounding (Lớp kiểm duyệt an toàn không chặn được các tiêu chí phân biệt đối xử trái pháp luật; quy tắc nghiệp vụ/rule-based filter được đưa vào hệ thống mà không qua kiểm tra tính tuân thủ pháp lý lao động). |
| Harm xảy ra là gì? | Hơn 200 ứng viên bị tước đoạt cơ hội việc làm và thu nhập một cách bất công dù có đủ năng lực sư phạm; tổn thương tinh thần khi bị gạt bỏ vì lý do tuổi tác - đã diễn ra trên thực tế. |
| Harm lens | Mất cơ hội việc làm và tổn hại phẩm giá do phân biệt đối xử. |
| Severity | High (tác động trực tiếp đến thu nhập và vi phạm luật nhân quyền/lao động liên bang). |
| Scale | Medium (xác nhận tác động trực tiếp lên hơn 200 ứng viên tại thị trường Mỹ). |
| Probability | High (xác suất xảy ra là 100% đối với bất kỳ ứng viên nào thuộc nhóm tuổi bị lọc, do thuật toán chạy tự động theo quy tắc cứng). |
| Frequency | High (diễn ra liên tục trên mọi lượt ứng tuyển nộp vào hệ thống trong suốt thời gian phần mềm hoạt động). |
| Vì sao? | Đánh giá dựa trên hồ sơ pháp lý công khai của EEOC tại Tòa án Liên bang Hoa Kỳ; đây là vụ kiện phân biệt đối xử đầu tiên liên quan đến phần mềm tuyển dụng tự động/AI mà EEOC giải quyết thành công, chứng minh rủi ro hiện hữu của việc thiếu kiểm toán tính công bằng trong HR Tech. |
