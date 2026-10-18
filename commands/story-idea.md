---
description: Chuyển ý tưởng video thô thành kịch bản có cấu trúc (Toolkit 1)
argument-hint: [ý tưởng video thô]
---

Chuyển ý tưởng video thô thành kịch bản có cấu trúc đầy đủ, đúng tông giọng và mục tiêu của người dùng.

<args>$ARGUMENTS</args>

## Process
1. Kích hoạt skill `video-idea-to-script`
2. Nhận ý tưởng thô → xác nhận persona (tông giọng theo cặp, nền tảng/độ dài, mục tiêu) → đề xuất 2-3 hướng khai triển → checkpoint xác nhận → dựng bảng cảnh đầy đủ
3. Output: 1 bảng cảnh (Scene/Dialogue/Visual/Text overlay), hỏi có muốn chuyển sang `/story-review` ngay không

## Examples
- `/story-idea nhiều người tiết kiệm sai cách` — Bắt đầu từ 1 câu ý tưởng thô
- `/story-idea [dán đoạn ghi chú/thoại rời rạc]` — Bắt đầu từ ghi chú chưa gọt

## Tips
- Không cần gọt sẵn ý tưởng trước khi gõ lệnh — việc gọt là việc của skill này
- Nếu đã chạy cho nhân vật này trước đó trong phiên, persona sẽ được gợi ý lại từ lần trước
