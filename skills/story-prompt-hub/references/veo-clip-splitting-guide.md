# Tách nhịp hình & khuôn prompt video (Google Flow / Veo)

Đọc file này trước khi viết prompt ở Giai đoạn 1 và Giai đoạn 2 của SKILL.md.

## Vì sao phải tách nhịp

Veo (model video trong Google Flow) chỉ animate được **1 frame tĩnh cho mỗi lần tạo clip**. Nếu 1 cảnh trong bảng cảnh gốc chứa nhiều hơn 1 "nhịp hình" riêng biệt — ví dụ nhân vật nói xong rồi cảnh cắt sang hành động khác, hoặc có 2-3 hành động không gói được trong 1 frame tĩnh — cảnh đó phải được tách thành nhiều frame/clip con trước khi sinh prompt, nếu không sẽ thiếu frame khi sang Giai đoạn 2.

## Quy ước đặt tên

Cảnh gốc đánh số theo bảng cảnh (Scene 01, 02, 03...). Khi 1 cảnh cần tách, đặt tên các frame con bằng chữ cái thường nối liền: `03a`, `03b`, `03c`... Các cảnh không cần tách giữ nguyên 1 frame = 1 cảnh.

**N ở Giai đoạn 1 (tổng số prompt ảnh/storyboard) phải bằng tổng số frame SAU KHI đã tách — không phải số dòng trong bảng cảnh gốc.** Giai đoạn 2 (prompt video) sinh 1:1 theo đúng N này.

## Khuôn cho mỗi clip (Giai đoạn 2)

Mỗi clip viết theo đúng khuôn, bắt đầu bằng dòng nhãn `CLIP <id> — [Tên Nhãn]` (id khớp đúng với tên frame đã đặt ở Giai đoạn 1, ví dụ `05b`).

**Ngôn ngữ:** Toàn bộ nội dung prompt viết bằng **tiếng Anh** để Flow/Veo xử lý chính xác hơn — **ngoại trừ** `[Tên Nhãn]` và nội dung `DIALOGUE` (lời thoại thật sẽ được nói/lip-sync) vẫn giữ nguyên **tiếng Việt**.

```
CLIP <id> — [Tên Nhãn bằng tiếng Việt]
MOTION: <tiếng Anh, mô tả CHI TIẾT — trường quan trọng nhất, xem hướng dẫn riêng bên dưới>
CAMERA: <tiếng Anh — loại chuyển động camera>
DIALOGUE: <tiếng Việt — lời thoại gốc của clip này, ghi rõ loại — xem bên dưới>
AUDIO: <tiếng Anh — âm thanh nền của clip, luôn phải có>
DURATION: <tiếng Anh, số giây ước lượng cho clip này>
```

Không thêm mô tả ngoại hình/bối cảnh trong prompt video — frame tĩnh ở Giai đoạn 1 đã quyết định việc đó.

## MOTION — trường quan trọng nhất, phải viết kỹ

MOTION là yếu tố quyết định Flow/Veo có tạo đúng ý tưởng ban đầu hay không — mô tả sơ sài, chung chung dễ khiến AI "đoán" sai hành động. Khi viết MOTION:

- **Mô tả theo trình tự thời gian**: điều gì xảy ra đầu tiên, tiếp theo, kết thúc ra sao trong clip — không viết 1 câu chung chung cho cả clip.
- **Nêu rõ bộ phận cơ thể/hành động cụ thể** (tay, đầu, ánh mắt, dáng người, tốc độ cử động) thay vì mô tả cảm xúc trừu tượng.
- **Nêu tốc độ/nhịp chuyển động** (slow, sudden, gradual...) nếu ảnh hưởng đến cảm xúc cảnh.
- **Giữ nhất quán với mô tả frame tương ứng ở Giai đoạn 1** — không tự thêm hành động mới không có trong frame gốc.

Ví dụ MOTION viết sơ sài (tránh): `"Person stands up and drinks water."`
Ví dụ MOTION viết đủ chi tiết (nên làm): `"From the static frame, the person pushes back the chair with one hand, rises slowly, takes two steps toward the counter, picks up a glass with the right hand, tilts it to drink, pauses briefly mid-sip."`

## Rẽ nhánh DIALOGUE — lip-sync hay voiceover

- **Nhân vật xuất hiện nói trực diện trong frame** → ghi `DIALOGUE (on-camera, lip-synced): "..."` (lời thoại tiếng Việt). Veo ước lượng khẩu hình từ text; khớp chính xác với audio thật được xử lý ở bước dựng (Capcut), không phải ở đây.
- **Nhân vật không xuất hiện nói trong frame này** (cảnh cắt/B-roll, giọng kể chạy đè lên) → ghi `DIALOGUE (voiceover, không lip-sync): "..."` (lời thoại tiếng Việt). Tránh để model cố khớp khẩu hình cho nhân vật không nói trong frame.

AUDIO không bao giờ để trống, kể cả khi không có gì đặc biệt — ghi tối thiểu tương đương `"natural room tone, no background music"`.

## Nguyên tắc khóa nguồn

Lời thoại dùng cho prompt video (Giai đoạn 2) và prompt audio (Giai đoạn 3) phải đến từ **cùng một bảng cảnh đã chốt**. Nếu sửa câu chữ sau khi đã tạo video, khẩu hình (ước lượng từ text cũ) sẽ lệch với audio thật khi ghép — phải tạo lại từ đầu, không sửa chắp vá.
