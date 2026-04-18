---
name: video-qa
description: Kiểm tra chất lượng video AI Mèo Ú trước khi đăng TikTok theo checklist chuẩn
---

# Goal

Đánh giá chất lượng video AI Mèo Ú Nấu Ăn theo checklist chuẩn, phát hiện lỗi, và đưa ra khuyến nghị trước khi đăng TikTok.

# Instructions

1. **Kiểm tra nhân vật**: Mèo Ú có nhất quán (hình dáng, màu sắc, tỷ lệ) so với Character Bible?
   - ⚠️ **Kiểm tra độ mập**: Mèo Ú PHẢI siêu mập (ultra-chubby), bụng khổng lồ gần chạm đất, chân ngắn cũn cỡn. Nếu mèo trông gầy/thon → ❌ FAIL ngay
   - Má phính, cằm đôi, mặt tròn to
   - ❌ KHÔNG mũ, KHÔNG khăn, KHÔNG trang phục — mèo trần tự nhiên
   - Style semi-realistic, KHÔNG Pixar, KHÔNG anime
   - Tham chiếu: `project/nhan-vat/MEO_U_CHARACTER_BIBLE.md`
2. **Kiểm tra nội dung**: Flow nấu ăn có rõ ràng không? Có lỗi AI rõ ràng (tay thừa, méo hình)?
3. **Kiểm tra kỹ thuật**: Độ phân giải ≥ 1080x1920 (9:16)? Thời lượng phù hợp (15-60s)? Âm thanh ổn?
4. **Kiểm tra TikTok**: Caption hấp dẫn? Hashtag đúng (5-8)? Thumbnail bắt mắt? Giờ vàng đăng?
5. **Đánh giá tổng thể**: ✅ Pass / ⚠️ Cần sửa / ❌ Làm lại
6. **Lưu kết quả** vào `project/qa/ket-qua/YYYY-MM-DD_video-[ten].md`

# Examples

**Output format**:
```markdown
# QA Report: Video "Mèo Ú Làm Phở"
- Ngày: 2026-03-25
- Đánh giá: ⚠️ Cần sửa

## Checklist
- [x] Nhân vật nhất quán
- [x] Flow nấu ăn rõ
- [ ] ❌ Lỗi AI: tay phải có 6 ngón ở giây 12
- [x] Độ phân giải OK
- [ ] ⚠️ Caption chưa có CTA

## Khuyến nghị
1. Re-generate đoạn giây 10-15 (lỗi tay)
2. Thêm CTA: "Follow để xem Mèo Ú nấu gì tiếp!"
```

# Constraints

- PHẢI kiểm tra TỪNG mục trong checklist — không bỏ qua
- PHẢI ghi rõ timestamp nếu phát hiện lỗi AI
- KHÔNG đánh giá ✅ Pass nếu có bất kỳ lỗi AI nào về hình ảnh
- KHÔNG đánh giá ✅ Pass nếu Mèo Ú trông gầy hoặc thon — PHẢI siêu mập
- PHẢI đọc `project/nhan-vat/MEO_U_CHARACTER_BIBLE.md` trước khi QA
- Kết quả QA PHẢI lưu vào `project/qa/ket-qua/`
