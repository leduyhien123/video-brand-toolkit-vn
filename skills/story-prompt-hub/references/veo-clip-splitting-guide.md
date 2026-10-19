# Tách nhịp hình & khuôn prompt video (Google Flow / Veo)

Đọc file này trước khi viết prompt ở Giai đoạn 1 và Giai đoạn 2 của SKILL.md.

## Vì sao phải tách nhịp

Veo (model video trong Google Flow) chỉ animate được **1 frame tĩnh cho mỗi lần tạo clip**. Nếu 1 cảnh trong bảng cảnh gốc chứa nhiều hơn 1 "nhịp hình" riêng biệt — ví dụ nhân vật nói xong rồi cảnh cắt sang hành động khác, hoặc có 2-3 hành động không gói được trong 1 frame tĩnh — cảnh đó phải được tách thành nhiều frame/clip con trước khi sinh prompt, nếu không sẽ thiếu frame khi sang Giai đoạn 2.

## Quy ước đặt tên

Cảnh gốc đánh số theo bảng cảnh (Scene 01, 02, 03...). Khi 1 cảnh cần tách, đặt tên các frame con bằng chữ cái thường nối liền: `03a`, `03b`, `03c`... Các cảnh không cần tách giữ nguyên 1 frame = 1 cảnh.

**N ở Giai đoạn 1 (tổng số prompt ảnh/storyboard) phải bằng tổng số frame SAU KHI đã tách — không phải số dòng trong bảng cảnh gốc.** Giai đoạn 2 (prompt video) sinh 1:1 theo đúng N này.

## Khuôn cho mỗi clip (Giai đoạn 2)

Mỗi clip viết theo đúng khuôn, bắt đầu bằng dòng nhãn `CLIP <id> — [Tên Nhãn]` (id khớp đúng với tên frame đã đặt ở Giai đoạn 1, ví dụ `05b`; Tên Nhãn là mô tả ngắn bằng tiếng Việt):

```
CLIP <id> — [Tên Nhãn]
MOTION: <chuyển động từ frame tĩnh — hành động, biểu cảm, thay đổi gì trong khung hình>
CAMERA: <loại chuyển động camera — tĩnh/pan/push-in/zoom...>
DIALOGUE: <lời thoại của clip này, ghi rõ loại — xem bên dưới>
AUDIO: <âm thanh nền của clip — luôn phải có, kể cả khi chỉ là "tiếng phòng tự nhiên, không nhạc">
DURATION: <số giây ước lượng cho clip này — dựa theo độ dài lời thoại (pacing ~2.5-3 từ/giây tiếng Việt) nếu có DIALOGUE, hoặc độ dài hành động nếu là clip không thoại. Kiểm tra lại với giới hạn thời lượng/clip mà Google Flow đang cho phép trước khi dán, vì giới hạn này có thể thay đổi theo phiên bản>
```

Không thêm mô tả ngoại hình/bối cảnh trong prompt video — frame tĩnh ở Giai đoạn 1 đã quyết định việc đó.

## Rẽ nhánh DIALOGUE — lip-sync hay voiceover

- **Nhân vật xuất hiện nói trực diện trong frame** → ghi `DIALOGUE (on-camera, lip-synced): "..."`. Veo ước lượng khẩu hình từ text; khớp chính xác với audio thật được xử lý ở bước dựng (Capcut), không phải ở đây.
- **Nhân vật không xuất hiện nói trong frame này** (cảnh cắt/B-roll, giọng kể chạy đè lên) → ghi `DIALOGUE (voiceover, không lip-sync): "..."`. Tránh để model cố khớp khẩu hình cho nhân vật không nói trong frame.

AUDIO không bao giờ để trống, kể cả khi không có gì đặc biệt — ghi tối thiểu "tiếng phòng tự nhiên, không nhạc nền".

## Nguyên tắc khóa nguồn

Lời thoại dùng cho prompt video (Giai đoạn 2) và prompt audio (Giai đoạn 3) phải đến từ **cùng một bảng cảnh đã chốt**. Nếu sửa câu chữ sau khi đã tạo video, khẩu hình (ước lượng từ text cũ) sẽ lệch với audio thật khi ghép — phải tạo lại từ đầu, không sửa chắp vá.
