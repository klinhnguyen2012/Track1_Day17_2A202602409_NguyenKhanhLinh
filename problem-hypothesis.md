# Problem Hypothesis — Case A: AI Tutor / Diagnostic Refresher

## 1. Solution — Gỡ hình thức cụ thể

**Solution directive (nguyên văn):** Thêm nút **“Tôi vẫn chưa hiểu”** vào bài học. Khi học viên bấm nút, AI Tutor sử dụng nội dung bài hiện tại, các câu trả lời gần đây và lịch sử học tập để: 1. Đặt 2–3 câu hỏi chẩn đoán ngắn. 2. Chọn một khái niệm nền để học viên ôn lại. 3. Tạo một phần giải thích ngắn. 4. Đưa học viên trở về bài đang học.

**Các chi tiết triển khai trong directive:** nút bấm, AI Tutor, số lượng câu hỏi, nguồn dữ liệu và luồng quay lại bài.

**Capability trung tính:** Giúp người học xác định điều đang cản họ hiểu một phần bài học và tiếp cận sự hỗ trợ phù hợp để tiếp tục học.

## 2. Change — Chuỗi thay đổi được kỳ vọng

**Giả định của solution:**

```text
Có lúc người học không hiểu một phần bài
→ họ nhận ra mình cần trợ giúp và chủ động yêu cầu
→ họ xác định rõ hơn chỗ vướng
→ họ ôn hoặc được giải thích đúng phần cần thiết
→ họ quay lại và tiếp tục bài đang học
```

| Mắt xích | Loại | Điều cần kiểm tra |
| --- | --- | --- |
| Có hỗ trợ ngay tại thời điểm người học vướng | Output của solution | Người học có thật sự cần hỗ trợ tại thời điểm đó không? |
| Người học chủ động yêu cầu trợ giúp | Thay đổi hành vi | Khi vướng, họ có nhận ra và muốn dừng để xử lý không? |
| Người học xác định được nguyên nhân và xử lý chỗ vướng | Kết quả trung gian | Nguyên nhân có phải thiếu khái niệm nền không? |
| Người học tiếp tục bài với mức hiểu tốt hơn | Outcome kỳ vọng | Họ có tiếp tục và áp dụng được phần vừa học không? |

Nếu người học bỏ qua chỗ chưa hiểu, tự xử lý đủ tốt bằng cách hiện tại hoặc vướng vì lý do khác, chuỗi thay đổi trên có thể không xảy ra.

## 3. Actor — Các nhóm liên quan

| Actor | Họ đang làm gì? | Pain hoặc hậu quả có thể có | Lợi ích có thể có |
| --- | --- | --- | --- |
| Học viên | Học một bài và cố hiểu phần đang gặp | Mất thời gian, ngắt tiến độ hoặc tiếp tục khi chưa hiểu | Xác định chỗ vướng và tiếp tục học |
| Giảng viên/người thiết kế bài học | Giải thích, sắp xếp và hỗ trợ nội dung học | Khó biết điểm nào trong bài khiến người học vướng | Nhận biết phần nội dung cần cải thiện hoặc hỗ trợ |
| Người hỗ trợ học tập, nếu có | Trả lời thắc mắc của học viên | Có thể nhận yêu cầu thiếu ngữ cảnh | Hiểu rõ hơn học viên đang cần gì |

**Actor chọn điều tra trước:** Học viên từng gặp một phần bài học không hiểu trong bảy ngày gần đây và đã tìm cách xử lý.

**Lý do:** Đây là người trực tiếp trải nghiệm tình huống được directive nhắm tới. Phỏng vấn họ có thể làm rõ tình huống, hành vi thực tế, workaround và hậu quả. Các actor khác vẫn là nhánh cần xem xét nếu evidence cho thấy pain chính nằm ở việc thiết kế hoặc hỗ trợ bài học.

## 4. Situation & Job

**Situation giả định:** Khi đang học một bài và gặp một đoạn, khái niệm hoặc câu hỏi mà mình chưa hiểu, học viên muốn hiểu đủ để tiếp tục việc học. Họ có thể đọc lại, xem ví dụ, hỏi người khác, tìm nguồn khác hoặc bỏ qua; cách làm thực tế phải được xác minh qua phỏng vấn.

**JTBD Hypothesis:** Khi gặp một phần bài học chưa hiểu trong lúc đang học, tôi muốn tìm ra chính xác mình vướng ở đâu và xử lý chỗ vướng đó, để có thể tiếp tục bài với sự hiểu biết đủ dùng cho bước tiếp theo.

Job này vẫn tồn tại dù không có AI Tutor hay nút “Tôi vẫn chưa hiểu”.

## 5. Pain — Hai cách giải thích cạnh tranh

**Pain Hypothesis A — Thiếu nền tảng:** Khi gặp một phần bài chưa hiểu, học viên khó tiếp tục vì thiếu một khái niệm nền nhưng chưa biết chính xác mình thiếu gì. Họ có thể mất thời gian tìm kiếm, hỏi sai trọng tâm hoặc tiếp tục với lỗ hổng kiến thức.

**Pain Hypothesis B — Cách trình bày của bài chưa phù hợp:** Khi gặp một phần bài chưa hiểu, học viên đã có kiến thức nền cần thiết nhưng cách giải thích, ví dụ hoặc trình tự trong bài không giúp họ kết nối ý. Họ phải tìm một cách giải thích khác hoặc chờ người khác diễn giải lại.

**Giả thuyết ưu tiên điều tra trước:** A, vì solution directive đặt trọng tâm vào chẩn đoán và ôn khái niệm nền. **Đây là giả định của directive, không phải bằng chứng rằng A đúng.** Khi phỏng vấn cần mở khả năng B hoặc một nguyên nhân khác xuất hiện.

## 6. Evidence — Điều cần tìm qua sự kiện đã xảy ra

| Cần kiểm tra | Evidence làm giả thuyết A đáng tin hơn | Evidence khiến nhóm nghi ngờ hoặc sửa A |
| --- | --- | --- |
| Situation có thật | Học viên kể được một lần cụ thể trong bảy ngày gần đây, nêu bài học, điểm vướng và diễn biến | Không nhớ được sự kiện cụ thể; tình huống được mô tả chỉ là dự đoán |
| Pain có ý nghĩa | Họ dành thời gian hoặc công sức đáng kể để xử lý; việc học bị ngắt hoặc sai ở bước sau | Họ giải quyết nhanh, không ảnh hưởng đến việc học |
| Workaround tồn tại | Họ đã đọc lại, tìm tài liệu, hỏi người khác hoặc thử cách khác để xác định phần thiếu | Họ không thấy cần xử lý hoặc không làm gì thêm |
| Consequence tồn tại | Có hậu quả cụ thể: chậm tiến độ, làm sai, bỏ dở hoặc phải quay lại sau | Không có hậu quả quan sát được dù chưa hiểu ngay |
| Pattern có lặp | Những sự kiện tương tự xuất hiện ở nhiều bài hoặc nhiều lần gần đây | Chỉ là một sự cố đơn lẻ, hiếm gặp |
| Nguyên nhân là thiếu nền tảng | Khi truy lại trình tự, họ nhận ra một khái niệm trước đó cần cho phần đang học | Họ hiểu khái niệm nền nhưng cần ví dụ/cách trình bày khác; hoặc vướng vì thiếu thời gian, động lực hay vấn đề kỹ thuật |

**Chưa có evidence thực tế.** Không điền quote, tần suất hoặc kết luận cho đến khi nhóm có bản ghi và notes từ phỏng vấn.

## Problem Hypothesis mang sang Chặng 2

**Bản nháp:** Trong lúc học một bài, một số học viên gặp phần chưa hiểu và khó xác định khái niệm nền cần ôn, khiến họ phải tốn công tìm cách tháo gỡ hoặc không thể tiếp tục bài với mức hiểu cần thiết.

**Điều phải đúng để giả thuyết đứng vững:** Có những sự kiện gần đây mà học viên thật sự vướng; thiếu kiến thức nền là barrier đáng kể; họ đã cố xử lý và chịu một hậu quả có ý nghĩa.

**Điều có thể khiến nhóm sửa hoặc bác bỏ:** Các sự kiện cho thấy chỗ vướng chủ yếu do cách trình bày, thiếu ví dụ, áp lực thời gian, mất tập trung hoặc lý do khác; học viên xử lý đủ tốt bằng cách hiện tại; hoặc việc chưa hiểu không gây hậu quả đáng kể.

## Solution Parking Lot

Các hướng dưới đây chỉ để giữ lại lựa chọn, chưa phải đề xuất triển khai.

| Hướng giải quyết có thể có | AI / Không sử dụng AI |
| --- | --- |
| Liên kết thủ công từ phần bài khó tới khái niệm nền và ví dụ liên quan | Không sử dụng AI |
| Bổ sung ví dụ và cách giải thích khác ngay trong bài | Không sử dụng AI |
| Tạo kênh hỏi đáp với giảng viên, trợ giảng hoặc bạn học | Không sử dụng AI |
| Cho người học tự chọn chủ đề cần ôn từ danh sách khái niệm nền | Không sử dụng AI |
| Dùng AI đặt câu hỏi chẩn đoán và gợi ý phần ôn phù hợp | AI |

## Việc nhóm cần quyết định sau khi so sánh ba bản nháp

- Actor nào thực sự nên điều tra trước?
- Có pain hypothesis nào khác ngoài A và B đáng giữ lại?
- Những dấu hiệu nào đủ mạnh để nhóm đổi giả thuyết ưu tiên?
- Câu chữ nào trong bản nháp này đang vượt quá evidence hiện có?
