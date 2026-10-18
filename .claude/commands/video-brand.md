---
name: video-brand
description: "Chạy quy trình dựng video AI thương hiệu cá nhân (kịch bản → review → prompt Flow/AI Studio)"
argument-hint: "[ý tưởng video thô]"
---
Read and execute the command file at `commands/video-brand.md` in the project root.

Arguments: $ARGUMENTS

Follow the full process defined in that command file:
1. Read `commands/video-brand.md` for the command spec
2. Read `agents/06-video-brand-agent.md` for the agent system prompt
3. Read `skills/story-idea/SKILL.md` for Bước 1
4. Read `skills/story-review/SKILL.md` for Bước 2
5. Read `skills/story-prompt-hub/SKILL.md` (và `skills/story-prompt-hub/references/`) for Bước 3
6. Execute the command and deliver output theo đúng thứ tự, dừng xin xác nhận giữa mỗi bước
