---
description: Quy trình sản xuất 1 video AI Mèo Ú Nấu Ăn từ ý tưởng đến đăng TikTok
---

# Quy trình Tạo Video AI Mèo Ú

## Objective
Hướng dẫn từng bước sản xuất 1 video TikTok về Mèo Ú Nấu Ăn bằng AI.
**Nhân vật PHẢI nhất quán** xuyên suốt mọi video.

## ⚠️ TRƯỚC KHI BẮT ĐẦU — Đọc Character Bible
// turbo
1. Đọc `project/nhan-vat/MEO_U_CHARACTER_BIBLE.md` — nguồn sự thật duy nhất
2. Xác nhận: Visual DNA, Negative Prompts, Cooking Behaviors đã nắm rõ
3. ⚠️ Đặc điểm cốt lõi: Mèo Ú SIÊU MẬP, mèo trần tự nhiên (❌ không mũ/khăn), style semi-realistic, bối cảnh đồng quê VN
4. Nếu có Master Image → chuẩn bị sẵn để upload làm Reference

## Phase 1: Kịch bản (3 phút)
4. Chọn món ăn / ý tưởng
5. Viết brief video → lưu `project/briefs/dang-lam/YYYY-MM-DD_video-[ten-mon].md`
6. Brief bao gồm: tên món, chia shots (5-10 shots × 8s), mood, biểu cảm Mèo Ú mỗi shot
7. Chọn Cooking Behaviors phù hợp từ Character Bible cho mỗi shot

## Phase 2: Viết Prompt (5 phút)
8. Dùng skill `/prompt-writer` — BẮT BUỘC Template 7 Lớp
9. Mỗi shot = 1 prompt riêng với:
   - Camera + Subject (Visual DNA hoặc "from reference") + Action + Environment + Lighting + Style + Audio
   - Negative prompts (nguyên văn từ Character Bible)
   - Cooking Behavior phù hợp giai đoạn nấu
10. **1 hành động/shot** — KHÔNG gộp nhiều hành động

## Phase 3: Tạo AI Content (7 phút thao tác)
11. Upload Master Image Mèo Ú làm Reference/Ingredient trên Veo 3.1
12. Paste prompt từng shot → generate
13. Mở nhiều tab → render song song 5+ shots
14. Nếu cần ảnh tĩnh (thumbnail) → Nano Banana Pro với Visual DNA

## Phase 4: Hậu kỳ CapCut (10 phút)
15. Import tất cả clips vào CapCut
16. Color grading: sáng +6-7, sắc nét +20
17. Thêm SFX/ASMR (Pixabay): tiếng xèo xèo, thái rau
18. Phụ đề tự động: font đậm, vàng/đỏ, giữa màn hình
19. Trending sound volume ~0 (trick thuật toán)
20. Nhạc nền nhẹ nhàng

## Phase 5: QA & Publish
// turbo
21. Chạy QA checklist (`/video-qa` skill)
22. **Kiểm tra nhất quán nhân vật**: Mèo Ú có giống nhau qua mọi shot không? Có đủ siêu mập không?
23. Viết caption + hashtag (3-5: 1 broad + 2 niche + 1 trending)
24. Đăng TikTok:
    - **T2-T5**: 17:00-21:00
    - **T6**: 15:00-22:00
    - **T7**: 10:00-13:00 hoặc 17:00
    - **CN**: 8:00-10:00 hoặc 20:00

## Phase 6: Log
25. Lưu video final → `output/published/`
26. Chuyển brief → `project/briefs/hoan-thanh/`
27. Ghi `CHANGELOG.md`
