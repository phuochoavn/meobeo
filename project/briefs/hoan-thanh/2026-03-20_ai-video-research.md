# Brief: Nghiên cứu AI Video — 3 phiên DeepSearch

> **Ngày**: 2026-03-20
> **Folder lưu kết quả**: `docs/02_ai_video/`
> **Trạng thái**: ⏳ Đang thực hiện

---

## Phiên 1 — Google Veo 3.1 (Công cụ chính)

### Prompt gửi DeepSearch:

```
Đóng vai một chuyên gia sản xuất nội dung video AI với kinh nghiệm thực tế trên TikTok và YouTube Shorts.

Nhiệm vụ: Phân tích toàn diện Google Veo 3 (và phiên bản mới nhất nếu có) — công cụ tạo video AI của Google, trong bối cảnh sản xuất video ngắn dạng hoạt hình cho TikTok.

Nghiên cứu chi tiết các khía cạnh sau:

1. **Khả năng kỹ thuật**: Độ phân giải tối đa, thời lượng video tối đa, tỷ lệ khung hình hỗ trợ (đặc biệt 9:16), FPS, chất lượng hình ảnh thực tế. So sánh Veo 3 với các phiên bản trước.

2. **Tính nhất quán nhân vật (Character Consistency)**: Đây là yếu tố quan trọng nhất — khả năng giữ một nhân vật (ví dụ: con mèo béo mập màu cam) giống nhau qua nhiều video khác nhau. Có tính năng reference image, seed, character ID, hay kỹ thuật nào khác không? Giới hạn hiện tại là gì?

3. **Prompt Engineering cho Veo**: Cách viết prompt tạo video hiệu quả nhất. Cấu trúc prompt tối ưu (mô tả hình ảnh, chuyển động, âm thanh). Các keyword/thuật ngữ đặc biệt mà Veo phản hồi tốt. Ví dụ prompt tạo nhân vật hoạt hình.

4. **Quy trình thực tế**: Cách truy cập Veo (qua API, AI Studio, Google Flow, hay ứng dụng nào). Chi phí sử dụng. Giới hạn số lần generate. Thời gian render.

5. **Kinh nghiệm cộng đồng**: Tips, tricks, và bài học từ các creator đã sử dụng Veo để tạo video TikTok. Các kênh/tài khoản đã thành công với video AI. Những lỗi phổ biến và cách tránh.

6. **Giới hạn và điểm yếu**: Những gì Veo KHÔNG làm được hoặc làm kém — ví dụ: rendering tay/ngón tay, chuyển động phức tạp, vật lý chất lỏng, text trong video.

Ràng buộc:
- Ưu tiên thông tin từ sau tháng 1/2026 và kinh nghiệm thực tế đã xác minh
- Bỏ qua các bài viết marketing chung chung từ Google — tập trung vào trải nghiệm thực
- Nếu tính năng nào chưa có hoặc chưa xác nhận, ghi rõ "Chưa xác nhận" thay vì suy đoán
- Phân biệt rõ giữa Veo 2, Veo 3, và phiên bản mới nhất

Trình bày dưới dạng báo cáo có cấu trúc Markdown với bảng thông số kỹ thuật và trích dẫn nguồn.
```

---

## Phiên 2 — So sánh công cụ AI Video

### Prompt gửi DeepSearch:

```
Đóng vai một nhà phân tích công nghệ video AI chuyên so sánh và đánh giá các nền tảng tạo video.

Nhiệm vụ: Xây dựng bảng ma trận so sánh toàn diện các công cụ tạo video AI hàng đầu năm 2025-2026, đặc biệt cho use case tạo video hoạt hình nhân vật (character animation) đăng TikTok.

Các công cụ cần so sánh: Google Veo 3, OpenAI Sora, Runway Gen-3/Gen-4, Kling AI, Hailuo AI (MiniMax), Pika Labs, Luma Dream Machine.

Trước khi viết báo cáo, hãy tự xác định 8 tiêu chí đánh giá quan trọng nhất cho use case "tạo video hoạt hình nhân vật ngắn cho TikTok", sau đó so sánh dựa trên đúng 8 tiêu chí đó. Gợi ý tiêu chí:
- Chất lượng hình ảnh & độ phân giải
- Character consistency (giữ nhân vật nhất quán)
- Thời lượng video tối đa
- Hỗ trợ 9:16 (vertical video)
- Chi phí sử dụng (free tier + paid)
- Tốc độ generate
- Khả năng kiểm soát chuyển động
- Dễ sử dụng & khả năng tiếp cận

Ngoài ra, phân tích:
1. **Combo tool tối ưu**: Nếu không tool nào hoàn hảo, sự kết hợp nào cho kết quả tốt nhất? (ví dụ: dùng tool A tạo frame → tool B animate)
2. **Xu hướng phát triển**: Tool nào đang phát triển nhanh nhất? Dự báo landscape 6 tháng tới.

Ràng buộc:
- Chỉ so sánh dựa trên dữ liệu thực tế và benchmark đã công bố — không suy đoán
- Nếu tool nào chưa ra mắt công khai hoặc chưa có dữ liệu, ghi "Dữ liệu không khả dụng"
- Ưu tiên trải nghiệm thực tế của creator hơn thông số marketing
- Ghi rõ ngày cập nhật thông tin cho mỗi tool (vì landscape thay đổi rất nhanh)

Trình bày bảng so sánh ma trận chính + phân tích chi tiết từng tool. Trích dẫn nguồn.
```

---

## Phiên 3 — Quy trình sản xuất video AI cho TikTok

### Prompt gửi DeepSearch:

```
Đóng vai một nhà sản xuất nội dung TikTok chuyên nghiệp có kinh nghiệm 2+ năm tạo video AI viral.

Nhiệm vụ: Nghiên cứu và xây dựng quy trình sản xuất video AI hoàn chỉnh (end-to-end workflow) cho kênh TikTok dạng nhân vật hoạt hình AI nấu ăn, từ ý tưởng đến đăng bài.

Nghiên cứu chi tiết:

1. **Quy trình sản xuất chuẩn**: Các bước từ A-Z để sản xuất 1 video AI ngắn (30-60 giây). Thời gian ước tính cho mỗi bước. Mục tiêu: tối ưu quy trình xuống dưới 30 phút/video.

2. **Toolchain khuyến nghị**: Bộ công cụ kết hợp cho pipeline hoàn chỉnh:
   - Tạo hình ảnh nhân vật (reference images)
   - Tạo video từ prompt hoặc image-to-video
   - Chỉnh sửa video (cắt, ghép, thêm text)
   - Thêm âm thanh, nhạc nền, voice-over
   - Tạo thumbnail/cover
   
3. **Batch production**: Kỹ thuật sản xuất hàng loạt — tạo 5-10 video cùng lúc thay vì từng video một. Cách tổ chức assets, templates, và prompt library.

4. **Case studies**: Phân tích 3-5 kênh TikTok AI thành công nhất (đặc biệt kênh về mèo, thú cưng, hoặc nấu ăn AI). Họ dùng toolchain gì? Đăng bao nhiêu video/tuần? Content strategy?

5. **Tối ưu cho TikTok**: Giờ đăng tốt nhất, tần suất đăng, chiến lược hashtag, cách viết caption viral, hook 3 giây đầu, trending sounds.

Ràng buộc:
- Tập trung vào kinh nghiệm thực tế đã xác minh, không lý thuyết suông
- Bỏ qua các bài viết "làm giàu từ AI" không có dẫn chứng cụ thể
- Nếu không tìm thấy case study cụ thể, ghi "Dữ liệu không khả dụng"
- Ưu tiên các công cụ miễn phí hoặc chi phí thấp

Trình bày dưới dạng hướng dẫn thực hành có cấu trúc, kèm bảng so sánh toolchain và trích dẫn nguồn.
```

---

## Sau khi nhận kết quả

| Phiên | Lưu kết quả vào |
|-------|-----------------|
| 1 | `docs/02_ai_video/gemini-veo/2026-03-20_veo-research-ket-qua.md` |
| 2 | `docs/02_ai_video/so-sanh-cong-cu/2026-03-20_so-sanh-ket-qua.md` |
| 3 | `docs/02_ai_video/quy-trinh/2026-03-20_workflow-ket-qua.md` |
