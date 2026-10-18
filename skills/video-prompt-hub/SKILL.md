---
name: video-prompt-hub
description: >
  Biến kịch bản video đã review xong thành prompt sẵn dùng cho Google Flow
  (storyboard + video) và Google AI Studio (audio TTS), giữ nhất quán nhân
  vật/bối cảnh xuyên suốt nhiều cảnh. Dùng skill này khi người dùng đã có 1
  bảng cảnh đã chốt (qua skill `video-idea-to-script` + `review-kich-ban-video-ngan`,
  hoặc tự viết tương đương) và muốn "sinh prompt", "tạo prompt cho Flow/Veo",
  "làm audio TTS", "chuyển kịch bản thành prompt ảnh/video/audio". Giả định
  ảnh nhân vật + bối cảnh cố định đã được tạo sẵn trên Google Flow (làm
  Reference khi tạo ảnh/video từng cảnh) — việc tạo ảnh nhân vật gốc không
  thuộc skill này. KHÔNG dùng skill này để viết hoặc review kịch bản — đó là
  việc của `video-idea-to-script` và `review-kich-ban-video-ngan`.
---

# Claude thành Prompt Hub

Đọc 2 file tham khảo trước khi bắt đầu: `references/veo-clip-splitting-guide.md` (Giai đoạn 1-2) và `references/gemini-tts-reference.md` (Giai đoạn 3).

## Nguyên tắc khóa nguồn — áp dụng cho cả 3 giai đoạn

Trước khi bắt đầu Giai đoạn 1, kịch bản dùng xuyên suốt phải là bản **đã chốt** (đã qua review, không còn thay đổi). Không sửa lời thoại giữa chừng sau khi đã generate bất kỳ giai đoạn nào — video lip-sync ở Giai đoạn 2 ước lượng khẩu hình theo đúng text lúc đó; sửa câu chữ sau ở Giai đoạn 3 sẽ làm khẩu hình lệch với audio thật khi ghép ở bước dựng. Muốn sửa chữ thì phải sửa lại kịch bản gốc và chạy lại cả 3 giai đoạn.

Nếu người dùng chưa có bảng cảnh đã chốt, đề nghị chạy qua `video-idea-to-script` rồi `review-kich-ban-video-ngan` trước — không tự bịa bảng cảnh để chạy tiếp.

## Giai đoạn 1 — Prompt cho Storyboard Studio (Google Flow)

Chỉ sinh prompt dùng công cụ Storyboard Studio có sẵn trong Flow. Việc tạo ảnh nhân vật/bối cảnh gốc đã có hướng dẫn riêng ngoài phạm vi skill này.

1. **Xác định điểm tách nhịp** — xem `references/veo-clip-splitting-guide.md`. Với mỗi cảnh trong bảng đã chốt, kiểm tra có nhiều hơn 1 "nhịp hình" riêng biệt không (Veo chỉ animate 1 frame tĩnh/lần). Nếu có, tách thành frame con, đặt tên `03a/03b`, `06a/06b/06c`... Nếu không, giữ 1 frame = 1 cảnh.
2. **Sinh prompt cho MỖI FRAME sau khi tách** — N = tổng số frame cuối cùng, không phải số dòng cảnh gốc. Mỗi prompt gồm: khối neo tổng quát (nhắc ngắn ai, bối cảnh chung, phong cách hình ảnh — không tả lại chi tiết ngoại hình vì ảnh Reference đã đảm nhiệm phần đó) + mô tả riêng của frame này (góc máy, hành động, biểu cảm, ánh sáng/khung cảnh cụ thể).

**Nếu cột Visual có đánh dấu `[overlay: ...]`:** đó là đồ họa dựng thêm ở bước dựng (Capcut), không phải footage — không đưa phần trong ngoặc vuông vào prompt Storyboard Studio, chỉ dùng phần mô tả footage thật đứng trước nó.

## Giai đoạn 2 — Prompt Video motion (1:1 với N frame ở Giai đoạn 1)

Theo đúng khuôn 4 dòng và quy tắc rẽ nhánh lip-sync/voiceover trong `references/veo-clip-splitting-guide.md`: `MOTION → CAMERA → DIALOGUE → AUDIO`, AUDIO luôn có mặt (không để trống).

## Giai đoạn 3 — 1 prompt Audio TTS duy nhất cho toàn kịch bản

Không tạo riêng từng cảnh — để giọng nói đồng nhất suốt video. Một prompt gồm:

1. **Audio Profile** — giọng nhân vật từ persona đã xác nhận ở `video-idea-to-script`. Nếu dùng Gemini TTS, chọn theo voice list thật trong `references/gemini-tts-reference.md`.
2. **Director's Note** — ưu tiên lấy từ góc "Đạo diễn lồng tiếng" của `review-kich-ban-video-ngan` nếu có. **Nếu góc đó bị bỏ qua** (kịch bản gốc không có style tag) → tự tổng hợp nhịp/cảm xúc từ persona + nội dung từng cảnh, và **nêu rõ đây là suy luận**, không để trống âm thầm.
3. Toàn bộ lời thoại nối theo đúng thứ tự kịch bản, dùng `<long pause>` giữa các cảnh để phân biệt ranh giới (xem `references/gemini-tts-reference.md` — đây là tag hợp lệ model nhận dạng được, không dùng ký hiệu tự chế như `[Scene 1]`).

Luôn nhắc người dùng nghe thử và tinh chỉnh lại sau khi tạo — xem phần "Giới hạn cần biết" trong `references/gemini-tts-reference.md`.

## Output cuối

- Giai đoạn 1: N prompt ảnh/storyboard (1 cho mỗi frame sau khi tách nhịp)
- Giai đoạn 2: N prompt video (1:1 với Giai đoạn 1, rẽ nhánh lip-sync/voiceover)
- Giai đoạn 3: 1 prompt audio duy nhất cho cả kịch bản, có `<long pause>` đánh dấu ranh giới cảnh để cắt khi dựng
