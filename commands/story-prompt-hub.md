---
description: Sinh prompt ảnh/video/audio cho Google Flow + AI Studio (Toolkit 3)
argument-hint: [kịch bản đã chốt]
---

Biến kịch bản đã review xong thành prompt sẵn dùng cho Google Flow (storyboard + video) và Google AI Studio (audio TTS).

<args>$ARGUMENTS</args>

## Process
1. Kích hoạt skill `story-prompt-hub`
2. Xác nhận kịch bản là bản đã chốt (qua `/story-review`) — không chạy trên bản còn có thể sửa
3. Giai đoạn 1 — prompt Storyboard Studio (tách nhịp nếu cần, N = tổng frame)
4. Giai đoạn 2 — prompt video motion 1:1 với N frame, rẽ nhánh lip-sync/voiceover
5. Giai đoạn 3 — 1 prompt audio TTS duy nhất cho cả kịch bản

## Examples
- `/story-prompt-hub [dán bảng cảnh đã chốt từ /story-review]`

## Tips
- Giả định ảnh nhân vật + bối cảnh cố định đã có sẵn trên Google Flow (làm Reference) — việc tạo ảnh gốc không thuộc lệnh này
- Không sửa lời thoại giữa chừng sau khi đã chạy lệnh này — sẽ làm khẩu hình lip-sync lệch với audio thật khi ghép ở Capcut
