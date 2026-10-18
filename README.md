# Video Brand Toolkit

3 skill Claude giúp dựng video AI ngắn để xây thương hiệu cá nhân — từ ý tưởng thô đến prompt sẵn dùng cho Google Flow (storyboard + video) và Google AI Studio (audio). Tổng quát hoàn toàn — không gắn cứng với 1 nhân vật/thương hiệu cụ thể nào, bạn tự khai báo persona của riêng mình.

| Skill | Việc gì |
|---|---|
| `story-idea` | Ý tưởng thô → kịch bản có cấu trúc (bảng Scene/Dialogue/Visual/Text overlay) |
| `story-review` | Review kịch bản theo 4 góc nhìn (Khán giả, Marketing, Đạo diễn lồng tiếng, Giữ gìn Thương hiệu) |
| `story-prompt-hub` | Sinh prompt Storyboard Studio → Video motion → Audio TTS cho Google Flow/AI Studio |

## Yêu cầu

- **Claude.ai bản Pro/Max/Team/Enterprise** (Skills cần "code execution" — không chạy trên bản Free)
- Đã có sẵn ảnh nhân vật + bối cảnh cố định tạo riêng trên Google Flow trước khi dùng `story-prompt-hub`

## Cài đặt trên claude.ai (web/app)

1. Mở **Customize** ở sidebar → **Plugins**
2. Chọn **Add marketplace**, dán URL repo này: `https://github.com/leduyhien123/video-brand-toolkit-vn`
3. 3 skill sẽ hiện trong danh sách — bấm cài đặt
4. Bắt đầu chat bình thường: mô tả ý tưởng video, Claude sẽ tự nhận diện và dùng đúng skill (hoặc gõ rõ "viết kịch bản cho ý tưởng: ..." để chắc chắn kích hoạt `story-idea`)

## Cài đặt trên Claude Code (tùy chọn, cho người dùng kỹ thuật)

```bash
/plugin marketplace add leduyhien123/video-brand-toolkit-vn
```

Repo này còn có sẵn lệnh riêng cho Claude Code (`agents/`, `commands/`, `.claude/commands/`):

- `/video-brand [ý tưởng]` — chạy nối tiếp cả 3 bước trong 1 phiên
- `/story-idea [ý tưởng]` — chỉ Bước 1
- `/story-review [kịch bản]` — chỉ Bước 2, chạy độc lập được
- `/story-prompt-hub [kịch bản đã chốt]` — chỉ Bước 3

## Thứ tự dùng (khuyến nghị)

1. `story-idea` — ra bảng cảnh
2. `story-review` — review, sửa nếu cần (chạy độc lập được nếu bạn tự viết kịch bản sẵn)
3. `story-prompt-hub` — ra prompt cho Flow/AI Studio

Không sửa lời thoại sau khi đã sinh prompt video ở bước 3 — sẽ làm khẩu hình lip-sync lệch với audio thật khi ghép ở bước dựng.
