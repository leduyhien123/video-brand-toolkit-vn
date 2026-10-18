---
description: Review kịch bản video đa góc nhìn (Toolkit 2) — chạy độc lập được
argument-hint: [kịch bản cần review]
---

Review kịch bản video ngắn theo 4 góc nhìn (Khán giả, Người làm Marketing, Đạo diễn lồng tiếng, Giữ gìn Thương hiệu).

<args>$ARGUMENTS</args>

## Process
1. Kích hoạt skill `story-review`
2. Kiểm tra độ đầy đủ (persona, mục tiêu, bảng cảnh đầy đủ) — nếu thiếu, đề nghị chạy `/story-idea` trước
3. Đọc hết 1 lượt → review theo 4 góc nhìn → "Khuyến nghị nhanh"
4. Hỏi rewrite 1 câu duy nhất ở cuối, sau khi đã trình bày hết báo cáo

## Examples
- `/story-review [dán bảng cảnh]` — Review kịch bản vừa viết từ `/story-idea`
- `/story-review [dán 1 đoạn/cảnh]` — Xin ý kiến riêng 1 đoạn, không cần full kịch bản

## Tips
- Chạy độc lập được, không bắt buộc phải qua `/story-idea` trước — nhưng nếu kịch bản thiếu persona/mục tiêu, lệnh sẽ đề nghị chạy `/story-idea` để review chính xác hơn
- Có thể hỏi riêng 1 góc nhìn cụ thể (VD: "chỉ cần góc nhìn khán giả thôi")
