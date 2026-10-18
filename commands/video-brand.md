---
description: Chạy nối tiếp quy trình 3 bước dựng video AI thương hiệu cá nhân
argument-hint: [ý tưởng video thô]
---

Chạy quy trình dựng video AI cho thương hiệu cá nhân, từ ý tưởng thô đến prompt sẵn dùng cho Google Flow/AI Studio.

<args>$ARGUMENTS</args>

## Actions
- `[ý tưởng]` — Chạy nối tiếp cả 3 bước trong 1 phiên (dừng xin xác nhận giữa mỗi bước)
- Muốn chạy riêng từng bước, dùng lệnh riêng thay vì `/video-brand`: `/story-idea` (Bước 1), `/story-review` (Bước 2, chạy độc lập được), `/story-prompt-hub` (Bước 3)

## Process
1. Kích hoạt Video Brand Agent
2. Bước 1 — skill `video-idea-to-script`: nhận ý tưởng thô, xác nhận persona, đề xuất hướng, checkpoint, dựng bảng cảnh
3. Hỏi xác nhận trước khi qua Bước 2
4. Bước 2 — skill `review-kich-ban-video-ngan`: review 4 góc nhìn, hỏi rewrite 1 lần ở cuối
5. Hỏi xác nhận trước khi qua Bước 3
6. Bước 3 — skill `video-prompt-hub`: sinh prompt theo 3 giai đoạn (storyboard → video → audio)

## Examples
- `/video-brand nhiều người tiết kiệm sai cách` — Chạy full pipeline từ ý tưởng thô
- `/story-review [dán kịch bản]` — Chỉ review 1 kịch bản đã viết sẵn, không cần chạy lại Bước 1

## Tips
- Mỗi bước có checkpoint xác nhận riêng — không bỏ qua để "nhanh hơn", vì chi phí sửa sau khi đã generate cao hơn nhiều chi phí dừng lại xác nhận
- Toolkit tổng quát hoàn toàn — không gắn cứng 1 nhân vật nào, mọi persona do người dùng tự khai báo mỗi phiên
