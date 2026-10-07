# Lab 21 — Phân tích rủi ro AI qua case study thực tế

- Họ và tên: Trần ĐÌnh Hinh
- MSSV: 2A202602399
- Lớp: Track1
- Ngành đã chọn: Media / news / social / political assistant (Thuật toán Mạng xã hội)

### 1. Industry Risk Snapshot

| Nội dung                                       | Đánh giá của tôi và lý do                                   |
| ----------------------------------------------- | ------------------------------------------------------------------ |
| Những tác hại chính có thể xảy ra        | Thuật toán gợi ý nội dung độc hại (tự hại, rối loạn ăn uống) cho thanh thiếu niên; khuếch đại tin giả và thao túng chính trị. Bóp méo nhận thức người dùng. |
| Mức độ high-stakes                           | **Cao**. Hệ thống tác động đến hàng tỷ người dùng hàng ngày. Việc thao túng tâm lý liên tục có thể dẫn đến hậu quả nghiêm trọng về sức khỏe tâm thần, tính mạng và bất ổn xã hội. |
| Dữ liệu nhạy cảm có thể được sử dụng | Dữ liệu hành vi duyệt web (thời gian dừng video, lượt thả tim, lịch sử tìm kiếm), độ tuổi, và các khuynh hướng tâm lý ẩn (suy luận từ nội dung tương tác). |
| Nhu cầu human review                           | **Cao**. Việc phân loại nội dung "độc hại" hay "tin giả" rất phức tạp về mặt ngữ cảnh. AI tự động lọc dễ bị "lách luật" nên cần con người kiểm duyệt ở chốt cuối để gỡ bỏ video nguy hiểm. |

### 2. Case study 1 — Thuật toán TikTok gợi ý nội dung độc hại cho thanh thiếu niên

#### Brief Case

- Tổ chức / sản phẩm AI: Thuật toán gợi ý "For You" của TikTok.
- Thời gian, địa điểm / bối cảnh: Báo cáo công bố tháng 12/2022 bởi tổ chức Center for Countering Digital Hate (CCDH).
- AI được dùng để làm gì: Đề xuất video cá nhân hóa để tối đa hóa thời gian giữ chân người dùng (User Engagement).
- Vấn đề hoặc sự kiện đáng chú ý: Thuật toán liên tục đẩy các nội dung liên quan đến rối loạn ăn uống và tự hại cho các tài khoản đóng giả là trẻ em 13 tuổi có biểu hiện tâm lý tổn thương.
- Số liệu có nguồn: Thuật toán TikTok gợi ý nội dung liên quan đến tự tử chỉ sau **2.6 phút** và nội dung rối loạn ăn uống sau **8 phút** kể từ lúc tạo tài khoản. Nội dung độc hại xuất hiện với tần suất **39 giây/lần**.
- Nguồn: Báo cáo "Deadly by Design" — Center for Countering Digital Hate (CCDH) — Tháng 12/2022 — https://counterhate.com/research/deadly-by-design/ (Báo Việt Nam: https://thanhnien.vn/tiktok-bi-kien-vi-goi-y-video-doc-hai-khien-2-thieu-nien-tu-tu-185241105111151613.htm)
- Phân biệt bằng chứng và nhận định: 
  - *Bằng chứng:* Các tài khoản test (13 tuổi) nhận video tự hại mỗi 39 giây (đã đo lường). 
  - *Nhận định:* Hệ thống này cố tình nhắm mục tiêu vào điểm yếu tâm lý của thanh thiếu niên để kiếm lợi.

#### Harm Map Worksheet

| Trường                     | Phân tích của tôi                                                             |
| ---------------------------- | --------------------------------------------------------------------------------- |
| High-risk moment             | Khi một người dùng trẻ tuổi có tâm lý bất ổn vô tình dừng lại xem một video buồn bã hoặc về cân nặng. |
| Stakeholder bị ảnh hưởng | Người dùng vị thành niên trực tiếp xem video, và gia đình/người thân của họ. |
| Failure mode                 | Harmful advice / Amplification (Khuếch đại nội dung gây hại). AI ưu tiên tương tác cao bất chấp tính chất độc hại của video. |
| Layer bắt đầu lỗi        | **Model / Safety**: Mô hình AI được tối ưu hóa quá mức cho "Watch Time" (thời gian xem) mà thiếu lớp bảo vệ (Safety layer) đủ mạnh để chặn nội dung nhạy cảm tự động phân phối. |
| Harm xảy ra là gì?        | Nguy cơ ảnh hưởng nghiêm trọng đến sức khỏe tâm thần và thể chất, dẫn đến trầm cảm, rối loạn ăn uống hoặc tự sát (Đã xảy ra trên thực tế). |
| Harm lens                    | Injury (Tổn hại thể chất) & Dignity loss (Tổn hại phẩm giá, tâm lý). |
| Severity                     | **Critical**. Hậu quả có thể đe dọa trực tiếp đến tính mạng (tự sát). |
| Scale                        | **High**. TikTok có hàng trăm triệu người dùng là thanh thiếu niên trên toàn cầu. |
| Probability                  | **High**. Nghiên cứu CCDH cho thấy 100% tài khoản "vulnerable" đều nhận được nội dung này rất nhanh. |
| Frequency                    | **High**. Xảy ra liên tục mỗi 39 giây như số liệu đo đạc. |
| Vì sao?                     | Thuật toán hoạt động dựa trên mục tiêu tối đa hóa lợi nhuận qua quảng cáo (giữ chân người xem càng lâu càng tốt), dẫn tới việc khai thác các điểm yếu tâm lý tự nhiên của con người. |

### 3. Case study 2 — Thuật toán TikTok khuếch đại tin giả về chiến sự Ukraine

#### Brief Case

- Tổ chức / sản phẩm AI: Hệ thống đề xuất và công cụ tìm kiếm của TikTok.
- Thời gian, địa điểm / bối cảnh: Nghiên cứu công bố tháng 3/2022, ngay khi xung đột Nga - Ukraine mới bùng nổ.
- AI được dùng để làm gì: Phân phối thông tin, tin tức thịnh hành (Trending) cho người dùng mới.
- Vấn đề hoặc sự kiện đáng chú ý: Thuật toán tự động "bơm" tin giả, cảnh quay cắt ghép từ video game hoặc sự kiện cũ vào luồng tin tức về chiến tranh cho người dùng mới, dù họ không chủ động tìm kiếm.
- Số liệu có nguồn: Người dùng mới bị phơi nhiễm với thông tin sai lệch về chiến tranh chỉ trong vòng **40 phút** sau khi tham gia. Gần **20%** video được AI tự động gợi ý qua thanh tìm kiếm về các chủ đề nóng chứa thông tin sai lệch.
- Nguồn: Nghiên cứu của NewsGuard — Tháng 03/2022 & 09/2022 — https://www.newsguardtech.com/misinformation-monitor/march-2022/ (Báo Việt Nam: https://baotintuc.vn/the-gioi/nhieu-tin-gia-ve-xung-dot-tai-ukraine-dang-lan-truyen-tren-tiktok-20220322131349503.htm)
- Phân biệt bằng chứng và nhận định:
  - *Bằng chứng:* Cứ 5 video AI gợi ý (20%) thì có 1 video là tin giả về chiến sự.
  - *Nhận định:* TikTok là nền tảng nguy hiểm nhất trong việc gieo rắc tin giả so với các mạng xã hội khác.

#### Harm Map Worksheet

| Trường                     | Phân tích của tôi                                      |
| ---------------------------- | ---------------------------------------------------------- |
| High-risk moment             | Khi người dùng mở ứng dụng để cập nhật thông tin về một sự kiện chính trị/xã hội điểm nóng đang diễn ra. |
| Stakeholder bị ảnh hưởng | Người tiếp nhận thông tin, cộng đồng xã hội, và các cá nhân/tổ chức bị bôi nhọ trong tin giả. |
| Failure mode                 | Misinformation / Hallucination (Hệ thống đề xuất "ảo giác" sự thật). Thuật toán không thể tự phân biệt được tin thật và tin cắt ghép. |
| Layer bắt đầu lỗi        | **Grounding / UX**: AI không có cơ sở dữ liệu đối chiếu sự thật (Grounding) trước khi phân phối video viral. Về UX, thiếu các nhãn dán cảnh báo "tin chưa kiểm chứng". |
| Harm xảy ra là gì?        | Người dùng tiếp nhận thông tin sai sự thật, bị dắt mũi dư luận, gây hoang mang, làm trầm trọng thêm chia rẽ chính trị. |
| Harm lens                    | Misinformation (Thông tin sai lệch diện rộng). |
| Severity                     | **High**. Ảnh hưởng trực tiếp đến nhận thức xã hội, an ninh quốc gia và các quyết định chính trị. |
| Scale                        | **High**. Các video tin giả thường đạt hàng triệu lượt xem rất nhanh nhờ thuật toán viral. |
| Probability                  | **High**. Tỷ lệ dính tin giả lên tới 20% khi tìm kiếm các từ khóa nổi bật. |
| Frequency                    | **High**. Hiện tượng này lặp lại ở gần như mọi sự kiện nóng (Bầu cử, đại dịch, chiến tranh). |
| Vì sao?                     | Thuật toán của TikTok ưu tiên tính "Virality" (Mức độ lan truyền nhanh) dựa trên cảm xúc mạnh của người xem, thay vì ưu tiên tính Xác thực (Accuracy). Tin giả thường giật gân nên dễ viral hơn tin thật. |

### 4. Case study 3 — Thuật toán TikTok phân biệt đối xử và hạn chế tương tác của nhóm người yếu thế

#### Brief Case

- Tổ chức / sản phẩm AI: Hệ thống kiểm duyệt và thuật toán gợi ý "For You" của TikTok.
- Thời gian, địa điểm / bối cảnh: Báo cáo rò rỉ công bố tháng 12/2019 bởi tổ chức quyền kỹ thuật số Netzpolitik.org.
- AI được dùng để làm gì: Lọc nội dung và quyết định video nào được phân phối rộng rãi trên trang "For You".
- Vấn đề hoặc sự kiện đáng chú ý: TikTok thiết lập AI và quy tắc tự động giới hạn (shadowban) khả năng tiếp cận của các video từ những người dùng bị nền tảng coi là "dễ bị tổn thương", bao gồm người khuyết tật, người thừa cân và cộng đồng LGBTQ+.
- Số liệu có nguồn: Các tài khoản bị gắn cờ tự động (Auto R - Restricted) sẽ bị chặn không cho xuất hiện trên trang "For You" và bị giới hạn lượt xem chỉ trong quốc gia của họ, khiến họ gần như không thể "viral" dù nội dung chất lượng. 
- Nguồn: Báo cáo của Netzpolitik.org — Tháng 12/2019 — https://netzpolitik.org/2019/discrimination-tiktok-curbed-reach-for-people-with-disabilities/ (Báo Việt Nam: https://dantri.com.vn/suc-manh-so/tiktok-thua-nhan-co-tinh-dim-hang-video-cua-nguoi-khuyet-tat-20191204121543169.htm)
- Phân biệt bằng chứng và nhận định:
  - *Bằng chứng:* Tài liệu nội bộ rò rỉ chứng minh TikTok có hướng dẫn gán nhãn "Auto R" để hạ reach đối với nhóm người khuyết tật/LGBTQ+.
  - *Nhận định:* Dù TikTok thanh minh đây là cách "bảo vệ" họ khỏi cyberbullying, thực chất nền tảng đang phân biệt đối xử và tước đi quyền tự do ngôn luận/cơ hội kinh tế của họ.

#### Harm Map Worksheet

| Trường                     | Phân tích của tôi                                      |
| ---------------------------- | ---------------------------------------------------------- |
| High-risk moment             | Khi một nhà sáng tạo nội dung thuộc nhóm thiểu số (khuyết tật, LGBTQ+, ngoại hình lệch chuẩn) đăng tải video với hy vọng lan tỏa cộng đồng. |
| Stakeholder bị ảnh hưởng | Các nhà sáng tạo nội dung thuộc nhóm yếu thế, cộng đồng người xem bị mất đi góc nhìn đa dạng. |
| Failure mode                 | Bias / Fairness (Thiên kiến / Thiếu công bằng). AI phân biệt đối xử dựa trên ngoại hình, tình trạng sức khỏe và xu hướng tính dục. |
| Layer bắt đầu lỗi        | **Model / Grounding**: Hệ thống được huấn luyện (hoặc can thiệp bằng rule) để đánh giá ngoại hình và đặc điểm cá nhân là "tiêu chuẩn rủi ro" cần hạn chế. |
| Harm xảy ra là gì?        | Người dùng bị cô lập, tước đi cơ hội phát triển sự nghiệp sáng tạo, bị tổn thương tâm lý vì cảm thấy bản thân "đáng bị giấu đi". |
| Harm lens                    | Opportunity loss (Mất cơ hội tiếp cận khán giả) & Dignity loss (Tổn hại phẩm giá). |
| Severity                     | **High**. Gây tổn hại tâm lý sâu sắc và tước đi cơ hội kinh tế bình đẳng của các nhóm yếu thế. |
| Scale                        | **High**. Ảnh hưởng đến hàng triệu người dùng thuộc nhóm thiểu số trên toàn cầu. |
| Probability                  | **High**. Giai đoạn này, chính sách được áp dụng triệt để lên các tài khoản bị AI/Moderator nhận diện. |
| Frequency                    | **High**. Bất kỳ video nào họ đăng lên cũng sẽ bị tự động bóp tương tác. |
| Vì sao?                     | TikTok muốn xây dựng một hình ảnh nền tảng "khát vọng, hoàn hảo" (aspirational) nên đã lạm dụng thuật toán để ẩn đi những người không phù hợp với tiêu chuẩn thẩm mỹ số đông, lấy cớ là "chống bắt nạt". |
