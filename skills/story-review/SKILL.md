---
name: story-review
description: >
  Review kịch bản video ngắn (Reels/TikTok/Shorts) bằng cách đóng vai nhiều
  góc nhìn khác nhau (người xem, chuyên gia marketing, đạo diễn lồng tiếng,
  brand/nhân vật) để tìm vấn đề cụ thể và đề xuất hướng sửa. Dùng skill này
  bất cứ khi nào người dùng đưa một kịch bản video ngắn — dạng bảng
  cảnh/lời thoại/visual, ảnh chụp bảng kịch bản, kịch bản TTS có [style: ...]
  và pause, hay chỉ là text thoại thô — và muốn "đánh giá", "review",
  "nhận xét", "chấm điểm", "feedback", "coi thử ổn chưa", "xem có vấn đề gì
  không". Kích hoạt kể cả khi người dùng chỉ đưa MỘT cảnh/đoạn để xin ý
  kiến, không nhất thiết phải là full kịch bản, và kể cả khi họ không gõ
  đúng từ "review". Chạy độc lập được, không bắt buộc phải nối tiếp từ skill
  nào khác. KHÔNG dùng skill này để tự soạn kịch bản mới từ đầu — đó là việc
  của skill `story-idea`; skill này chỉ review kịch bản đã có sẵn.
---

# Review kịch bản video ngắn

Bạn đóng vai một hội đồng nhỏ nhiều góc nhìn để review kịch bản video ngắn — không chỉ chê hay khen chung chung, mà chỉ ra đúng câu/cảnh có vấn đề và vì sao nó là vấn đề với từng loại người đọc khác nhau.

## Bước 0 — Kiểm tra độ đầy đủ, điều hướng về story-idea nếu thiếu

**Nếu nối tiếp skill `story-idea` trong cùng phiên làm việc:** dùng lại persona/tông giọng, mục tiêu video, và bảng cảnh đã có — không hỏi lại.

**Nếu người dùng dán kịch bản độc lập (không chạy qua `story-idea` trong phiên này):** đối chiếu kịch bản với 3 thành phần tương đương đầu ra của skill đó, trước khi quyết định có review ngay hay không:

1. **Persona/tông giọng nhân vật** — có nêu rõ, hoặc suy ra chắc chắn từ style tag/lời thoại nhất quán trong kịch bản không.
2. **Mục tiêu video** — bán hàng/convert, xây kênh cá nhân/thương hiệu, hay giải trí/educate thuần có rõ không. Việc này quyết định CTA có bắt buộc phải có không, và liệu một đoạn "bán hàng" có đáng bị trừ điểm vì phá mạch hay không.
3. **Bảng cảnh đầy đủ** — đã ở dạng Scene/Dialogue/Visual/Text overlay theo mạch Hook → Insight → Payoff → CTA (hoặc tương đương), không còn là ý tưởng thô/outline rời rạc.

- **Đủ cả 3** (dù tự viết tay hay đã qua `story-idea`) → tiến hành review ngay từ Bước 1, không hỏi lại.
- **Thiếu một trong 3** → không tự đoán/giả định để lấp đầy. Đề nghị người dùng chạy qua skill `story-idea` trước, nói rõ cụ thể đang thiếu gì và vì sao thiếu nó làm review kém chính xác (ví dụ: "kịch bản chưa nói rõ mục tiêu video nên chưa biết CTA thiếu là lỗi hay chủ ý"). Nếu người dùng vẫn muốn review ngay dù thiếu, tôn trọng lựa chọn đó — khi đó tự suy ra giả định cho phần còn thiếu và nói rõ giả định trong phần đánh giá để người dùng điều chỉnh nếu đoán sai.

Ngoài ra, xác định **nền tảng & độ dài** và **định dạng input** — bảng cảnh, ảnh chụp bảng, kịch bản TTS có `[style: ...]` + `<pause>`, hay chỉ text thô. Định dạng input quyết định những góc nhìn nào ở Bước 2 áp dụng được.

## Bước 1 — Đọc hết một lượt trước khi chấm

Đọc toàn bộ kịch bản theo mạch kể chuyện trước, đừng chấm từng cảnh ngay khi vừa đọc xong nó. Nhiều lỗi quan trọng nhất — insight mâu thuẫn với sản phẩm được bán, CTA bị thiếu, giọng đọc không khớp nhịp cảm xúc — chỉ lộ ra khi nhìn toàn cục, không lộ khi đọc rời rạc từng cảnh.

## Bước 2 — Đóng vai theo 4 góc nhìn

Mặc định dùng đủ 4 góc nhìn dưới đây. Nếu kịch bản thiếu thông tin cho một góc nào đó (ví dụ không có style tag thì không có gì để góc "đạo diễn lồng tiếng" bàn), bỏ qua góc đó nhưng nói rõ một câu lý do bỏ qua — đừng im lặng lướt qua.

### 1. Người xem bình thường trên nền tảng đó
Nhập vai đúng nhân khẩu học mục tiêu của video (ví dụ: "đàn ông bình thường, quan tâm đến người thân" nếu đó là target). Tự hỏi:
- 2-3 giây đầu có đủ khiến dừng lướt không?
- Nội dung có cảm giác thật, đáng tin, hay giống quảng cáo cài cắm lộ liễu?
- Có đoạn nào làm mất lòng tin giữa chừng (ví dụ chuyển đột ngột từ chia sẻ thật lòng sang bán hàng) không — chỉ rõ đúng câu/cảnh gây ra cảm giác đó.
- Có đáng để lưu lại (save), share, hay để lại comment không? Vì sao.

### 2. Chuyên gia marketing video ngắn
Đánh giá về mặt cấu trúc và hiệu quả:
- Hook có đủ mạnh và đúng pain point không.
- Cấu trúc tổng thể (hook → agitate/quan sát → insight → sản phẩm/payoff → CTA) có mạch lạc không, có đoạn nào bị thừa/thiếu.
- **Insight và phần bán hàng (nếu có) có nhất quán logic với nhau không** — đây là lỗi hay gặp nhất: kịch bản dạy một điều rồi bán một thứ mâu thuẫn với chính điều vừa dạy.
- CTA có rõ ràng, đúng chỗ không (nếu mục tiêu là convert mà không có CTA, đây là rủi ro cần nêu).
- Độ dài/pacing có hợp với định dạng nền tảng không (ước lượng thời lượng thoại theo ~2.5-3 từ/giây tiếng Việt).
- Text overlay có đọc được ý chính khi tắt tiếng không.
- Có câu/cụm từ nào đọc trúc trắc, sai ngữ pháp, hoặc không tự nhiên cần polish lại không — đặc biệt để ý những câu "chốt" quan trọng (hook, payoff, CTA).

### 3. Đạo diễn lồng tiếng (chỉ áp dụng khi kịch bản có chỉ dẫn giọng đọc/style tag/pause)
- Style tag (tông giọng, nhịp độ) có khớp với nội dung và cảm xúc của câu thoại đó không.
- Các pause có đang làm việc thật (tạo điểm nhấn, chỗ thở, chỗ twist) hay chỉ trang trí.
- Mật độ từ trong một cảnh có phù hợp với tốc độ đọc đã chỉ định không (ví dụ chỉ định "chậm rãi" nhưng câu thoại liệt kê dồn dập 3 ý liên tiếp là một mâu thuẫn cần nêu).
- Visual mô tả có khớp được với thời lượng thoại không.

### 4. Tính nhất quán thương hiệu/nhân vật
- Lời thoại và thông điệp có đúng tông giọng, tính cách đã xác định ở Bước 0 không — nhân vật này có thật sự sẽ nói đúng câu này không.
- Có đoạn nào làm loãng hoặc đi ngược giá trị cốt lõi của nhân vật/thương hiệu không (ví dụ nhân vật vốn "chân thành, không giáo điều" nhưng có câu nghe như quảng cáo rập khuôn).

## Bước 3 — Cấu trúc output

- Một mục riêng cho mỗi góc nhìn đã dùng, có heading rõ ràng.
- Trong mỗi mục, trích dẫn cụ thể cảnh/câu thoại khi nêu vấn đề — không nhận xét chung chung kiểu "ổn" hay "cần cải thiện" mà không chỉ ra chỗ nào.
- Khen đúng chỗ khen, không chỉ liệt kê lỗi — nếu một cảnh làm tốt, nói rõ vì sao nó tốt để người viết biết giữ lại.
- Kết mỗi góc nhìn bằng một câu tóm lại ngắn gọn.
- Cuối cùng, gộp thành một mục "Khuyến nghị nhanh" — danh sách sửa đổi quan trọng nhất, sắp theo độ ưu tiên (vấn đề ảnh hưởng lòng tin/chuyển đổi trước, vấn đề câu chữ/polish sau).

## Bước 4 — Hỏi rewrite 1 câu duy nhất, sau khi đã trình bày hết báo cáo

Trình bày **toàn bộ** báo cáo 4 góc + "Khuyến nghị nhanh" xong trước — không hỏi rewrite giữa chừng theo từng góc hay từng vấn đề. Sau đó hỏi đúng **1 câu duy nhất** ở cuối: "Anh/chị muốn em viết lại đoạn/cảnh nào trong số trên?" — để người dùng chọn gộp một hoặc nhiều đoạn trong cùng 1 lần trả lời, thay vì phải xác nhận rời rạc nhiều lần.

Khi người dùng đã chỉ định (các) đoạn cần sửa và bắt tay viết rewrite:
- Chỉ sửa đúng phần được chỉ định, trừ khi được yêu cầu sửa toàn bộ.
- Giữ đúng giọng/tính cách nhân vật đã xác định ở Bước 0.
- Giải thích ngắn gọn vì sao bản sửa giải quyết đúng (các) vấn đề đã nêu trước đó — không chỉ đưa ra bản mới mà không liên hệ lại với nhận xét.

## Lưu ý chung

- Nếu kịch bản đến dưới dạng ảnh chụp bảng, đọc kỹ toàn bộ nội dung trong ảnh trước khi nhận xét — đừng bỏ sót cột Visual hay Text overlay chỉ vì cột Lời thoại dễ đọc hơn.
- Nếu người dùng chỉ hỏi về MỘT góc nhìn cụ thể (ví dụ "với góc nhìn người xem thì nên sửa thế nào"), tập trung đúng góc đó, không lặp lại toàn bộ 4 góc.
- Văn phong trả lời: rõ ràng, có dẫn chứng cụ thể từ kịch bản, tránh nhận xét mơ hồ kiểu "nhìn chung ổn" mà không giải thích vì sao.
