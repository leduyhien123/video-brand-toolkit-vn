# Gemini TTS — tham khảo nhanh

Tổng hợp từ tài liệu chính thức `ai.google.dev/gemini-api/docs/speech-generation`. Đọc file này trước khi viết prompt Audio ở Giai đoạn 3 của SKILL.md.

## Cách điều khiển giọng đọc — 2 cấp độ

1. **Cấp lượt thoại (turn-level, kéo dài suốt câu)** — qua `speech_metadata.style`, mô tả bằng câu tự nhiên: `"cheerful and friendly"`, `"calm and relaxed"`, `"whispering"`, `"out of breath"`, `"sarcastic"`, `"speaking slowly"`.
2. **Tại một thời điểm (inline, sự kiện ngắn)** — chèn thẳng vào text bằng **dấu ngoặc nhọn**, không phải ngoặc vuông:
   - Âm thanh không lời: `<laugh>`, `<sigh>`, `<cough>`, `<breath>`, `<gasp>`, `<cry>`, `<chuckle>`, `<snort>`, `<yawn>`, `<throat-clearing>`
   - Khoảng dừng: `<short pause>`, `<long pause>`

Ví dụ nguyên văn từ tài liệu: `"Wait... <short pause> did you hear that? <sigh>"`

**Dùng `<long pause>` để phân biệt ranh giới giữa các cảnh khi gộp lời thoại toàn kịch bản vào 1 prompt audio duy nhất** — đây là tag hợp lệ model nhận dạng được, khác với việc tự chế ra ký hiệu riêng (ví dụ `[Scene 1]`) mà không có gì xác nhận model sẽ hiểu là annotation thay vì đọc thành lời.

## Multi-speaker

Hỗ trợ tối đa 2 người nói/request, mỗi lượt gắn `speaker` + `style` riêng. Chỉ dùng khi kịch bản thực sự có nhân vật thứ 2 lên tiếng (không tính nhân vật chỉ xuất hiện hình ảnh/B-roll, không nói).

## Giới hạn cần biết — đừng hứa hẹn quá

`speech_metadata.style` hiện chỉ áp dụng điều chỉnh prosody nhẹ (tốc độ, âm lượng) chứ chưa tạo ra "diễn xuất nhân vật" toàn diện như tài liệu mô tả. Luôn nhắc người dùng nghe thử bản dựng và sẵn sàng tinh chỉnh lại style/tag nếu chưa đúng ý, thay vì cam kết kết quả hoàn hảo ngay lần đầu.

## Nguồn

- https://ai.google.dev/gemini-api/docs/speech-generation
