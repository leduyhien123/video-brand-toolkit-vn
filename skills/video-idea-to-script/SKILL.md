---
name: video-idea-to-script
description: >
  Chuyển ý tưởng thô cho video ngắn (1 câu, ghi chú rời rạc, thoại chưa gọt,
  link/insight nhặt được — bất kỳ dạng nào) thành kịch bản có cấu trúc đầy đủ
  (bảng Scene/Dialogue/Visual/Text overlay). Tổng quát hoàn toàn — áp dụng
  được cho BẤT KỲ nhân vật/thương hiệu nào người dùng tự khai báo, không gắn
  cứng với 1 nhân vật cụ thể. Dùng skill này khi người dùng đưa một ý tưởng
  video còn thô và muốn "viết kịch bản", "lên script", "triển khai ý tưởng
  thành video", "bắt đầu làm video AI cho thương hiệu cá nhân". KHÔNG dùng
  skill này để review/chấm kịch bản đã có sẵn — đó là việc của skill
  review-kich-ban-video-ngan. KHÔNG dùng để sinh prompt ảnh/video/audio cho
  Google Flow hay Google AI Studio — đó là việc của skill video-prompt-hub.
---

# Từ ý tưởng thô đến kịch bản có cấu trúc

Bạn giúp người dùng biến một ý tưởng video còn thô thành kịch bản hoàn chỉnh, đúng tông giọng nhân vật và đúng mục tiêu của họ — theo đúng thứ tự 4 bước dưới đây, không bỏ bước hay đảo bước.

## Bước 1 — Nhận ý tưởng thô

Chấp nhận bất kỳ dạng input: 1 câu chủ đề ngắn, vài dòng ghi chú có ngữ cảnh, đoạn thoại rời rạc tự nói ra rồi gõ lại, link/insight nhặt được ở đâu đó. Không ép người dùng phải gọt sẵn ý tưởng theo khuôn nào trước khi đưa vào — việc gọt là việc của skill này.

## Bước 2 — Xác nhận Persona

Hỏi/gợi ý lại 3 trường sau **mỗi lần chạy**. Nếu trong phiên làm việc này đã từng hỏi (ví dụ đây là video thứ 2 trở đi với cùng nhân vật), chủ động gợi ý lại giá trị lần trước để người dùng chỉ cần gật đầu hoặc sửa nhanh — không bắt họ gõ lại từ đầu.

1. **Tông giọng/tính cách nhân vật** — gợi ý theo cặp kèm ví dụ câu thoại mẫu để người dùng biết chính xác đang chọn gì, hoặc để họ tự điền cặp riêng nếu không khớp:

   | Cặp tông giọng | Ví dụ câu thoại |
   |---|---|
   | Ấm áp – Hài hước khô | "Ba chục năm làm nghề này... à mà thôi, để tui kể từ từ." |
   | Sắc sảo – Thẳng thắn | "Bạn đang làm sai. Không phải vì bạn dốt, mà vì chưa ai nói thẳng cho bạn." |
   | Điềm đạm – Sâu lắng | "Có những điều... mình chỉ hiểu ra khi đã trả giá." |
   | Trẻ trung – Năng lượng cao | "Stop — bạn vừa làm đúng cái điều KHÔNG nên làm đó!" |
   | Dí dỏm – Gần gũi | Nói chuyện như bạn bè tám chuyện, hài tình huống. |
   | Nghiêm túc – Đáng tin | Giọng chuyên gia, dẫn chứng/dữ liệu, ít đùa. |
   | Tự tin – Quyết đoán | Khẳng định mạnh, ít rào trước đón sau. |
   | *(Khác)* | Người dùng tự điền cặp riêng nếu không cặp nào khớp. |

2. **Nền tảng & độ dài** — TikTok/Reels/Shorts, số giây mục tiêu. Quyết định pacing lời thoại ở Bước 4.
3. **Mục tiêu video** — bán hàng / xây kênh / educate. Quyết định loại CTA bắt buộc ở Bước 4.

## Bước 3 — Đề xuất 2-3 hướng khai triển, mỗi hướng một cơ chế kể chuyện khác nhau

Từ cùng 1 ý tưởng thô, đưa ra 2-3 hướng khai triển **khác nhau thật**, không chỉ đổi câu chữ của cùng một góc. Chọn cơ chế phù hợp với nội dung, ví dụ:

- **Kể chuyện cá nhân/trải nghiệm thật** — mở bằng 1 tình huống cụ thể đã xảy ra
- **Phản bác ngộ nhận phổ biến** — mở bằng điều "ai cũng nghĩ vậy nhưng sai"
- **Quan sát + câu hỏi gây tò mò** — mở bằng hiện tượng lạ rồi đặt câu hỏi

Mỗi hướng kèm 1 câu hook cụ thể + 1-2 câu mô tả mạch truyện, và 1 dòng nói rõ nó khác hướng kia ở đâu — để người dùng chọn dựa trên sự khác biệt thật, không phải cách diễn đạt.

## Bước 3.5 — Checkpoint xác nhận trước khi dựng full bảng cảnh

Sau khi người dùng chọn 1 hướng, **tóm tắt 3-4 dòng**: hook cụ thể → mạch triển khai chính → payoff → loại CTA dự kiến (theo mục tiêu đã khai ở Bước 2). Xin xác nhận hoặc hỏi có cần chỉnh hướng ngay tại đây — **trước khi** dựng full bảng cảnh. Chi phí sửa ở đây rất thấp so với phải làm lại cả bảng cảnh sau khi đã dựng xong.

## Bước 4 — Triển khai đầy đủ thành bảng cảnh

Dựng kịch bản theo khung: **Hook → Nỗi đau/Vấn đề (Agitate) → Insight/Giải pháp → Payoff → CTA**. Output là 1 bảng gồm 4 cột: **Scene / Dialogue / Visual / Text overlay**.

CTA luôn bắt buộc có mặt ở cả 3 mục tiêu, chỉ khác loại:

| Mục tiêu | Loại CTA |
|---|---|
| Bán hàng | Hành động cụ thể — mua / inbox / click link |
| Xây kênh | Tương tác — follow / comment / share / save |
| Educate | Nhẹ — lưu lại áp dụng / theo dõi phần tiếp theo |

Pacing lời thoại theo định dạng/độ dài đã khai ở Bước 2 (tiếng Việt ước lượng ~2.5-3 từ/giây).

**Quy ước cột Visual:** chỉ mô tả footage thật — hành động, biểu cảm, góc máy của nhân vật/bối cảnh sẽ xuất hiện trên khung hình. Không mô tả đồ họa/overlay dựng thêm sau (biểu đồ, hoạt hình chữ, icon minh họa) ngay trong phần mô tả footage. Nếu 1 cảnh cần thêm overlay dạng đó, ghi riêng ở cuối ô Visual trong ngoặc vuông, ví dụ: `[overlay: đồ thị năng lượng tụt dần]` — để skill `video-prompt-hub` biết phân biệt phần cần sinh prompt video thật với phần sẽ xử lý riêng ở bước dựng (Capcut).

## Output cuối & chuyển bước

Trả về 1 bảng cảnh hoàn chỉnh. Sau khi giao bảng cảnh, hỏi ngắn người dùng có muốn chuyển sang **review đa góc nhìn** (skill `review-kich-ban-video-ngan`) ngay không — đừng tự chuyển mà không hỏi, vì người dùng có thể muốn tự đọc lại trước.
