# 🐱🍳 Mèo Ú Nấu Ăn — Kênh TikTok AI

> Kênh TikTok về chú mèo ú đáng yêu nấu ăn, tạo bằng công nghệ AI (Google Gemini / Veo)

## 🎯 Mục tiêu kênh

- Tạo series video ngắn viral về mèo ú nấu ăn bằng AI
- Xây dựng nhân vật mèo ú có tính cách riêng, nhất quán
- Kết hợp yếu tố hài hước + cute + nấu ăn thực tế

## 👥 Đối tượng

- Gen Z & Millennials yêu mèo
- Người thích nội dung nấu ăn ngắn gọn
- Cộng đồng quan tâm AI content creation

## 🛠️ Công nghệ sử dụng

- **AI Video**: Google Gemini / Veo
- **AI Image**: Imagen / DALL-E
- **Nghiên cứu**: Google DeepSearch
- **Quản lý**: Antigravity AI Assistant

## 📊 KPI mục tiêu

- [ ] 100 video đầu tiên
- [ ] 10K followers trong 3 tháng đầu
- [ ] Tìm được art style nhất quán cho Mèo Ú
- [ ] Xây dựng quy trình sản xuất < 30 phút/video

---

## 📁 Hướng dẫn cấu trúc thư mục

### `docs/` — Tài liệu nghiên cứu

Tất cả kết quả nghiên cứu từ Google DeepSearch và các nguồn khác được lưu tại đây. Đặt tên file theo format: `YYYY-MM-DD_ten-chu-de.md`

| Thư mục | Mô tả | Ví dụ nội dung |
|---------|--------|----------------|
| `docs/01_prompting/deepsearch/` | Nghiên cứu kỹ thuật viết prompt cho DeepSearch | Template prompt, meta-research, best practices |
| `docs/01_prompting/gemini-video/` | Prompt tạo video AI (Gemini, Veo) | Cách mô tả nhân vật, hành động, bối cảnh |
| `docs/01_prompting/image-gen/` | Prompt tạo hình ảnh AI (Imagen, DALL-E) | Prompt thiết kế nhân vật, thumbnail |
| `docs/02_ai_video/gemini-veo/` | Nghiên cứu công cụ Google Veo / Gemini video | Tính năng, giới hạn, cách sử dụng |
| `docs/02_ai_video/so-sanh-cong-cu/` | So sánh các công cụ tạo video AI | Sora vs Runway vs Kling vs Hailuo |
| `docs/02_ai_video/quy-trinh/` | Workflow sản xuất video end-to-end | Từ ý tưởng → prompt → generate → edit → publish |
| `docs/03_nhan_vat/phong-cach/` | Phong cách hình ảnh nhân vật Mèo Ú | Art style, màu sắc, tỷ lệ cơ thể |
| `docs/03_nhan_vat/tinh-cach/` | Tính cách & biểu cảm của Mèo Ú | Cử chỉ đặc trưng, reaction khi nấu ăn |
| `docs/03_nhan_vat/tham-khao/` | Tham khảo từ kênh/nhân vật khác | Ảnh, link video, phân tích điểm hay |
| `docs/04_chien_luoc/thuat-toan/` | Thuật toán TikTok | Cách algo phân phối video, yếu tố ranking |
| `docs/04_chien_luoc/xu-huong/` | Format video đang trending | Trend sounds, templates, challenge viral |
| `docs/04_chien_luoc/doi-thu/` | Phân tích kênh đối thủ | Kênh mèo nấu ăn khác, kênh AI cooking |
| `docs/04_chien_luoc/lich-dang/` | Lịch đăng bài & content planning | Content calendar, series planning |
| `docs/05_nau_an/cong-thuc/` | Công thức nấu ăn | Món đơn giản, ngắn gọn, phù hợp video 30-60s |
| `docs/05_nau_an/xu-huong-am-thuc/` | Xu hướng ẩm thực trên TikTok | Món đang viral, food trends theo mùa |
| `docs/05_nau_an/trinh-bay/` | Kỹ thuật trình bày món ăn | Plating, góc quay, ánh sáng hấp dẫn |
| `docs/06_san_xuat/cong-cu/` | Hướng dẫn cài đặt & sử dụng tools | Setup Gemini API, phần mềm edit video |
| `docs/06_san_xuat/chinh-sua/` | Quy trình chỉnh sửa video | Cắt ghép, thêm text, nhạc, hiệu ứng |
| `docs/06_san_xuat/dang-bai/` | Quy trình đăng & tối ưu video | Caption, hashtag, giờ vàng, A/B test |

---

### `project/` — Quản lý dự án

Trung tâm điều hành dự án, bao gồm hướng dẫn cho trợ lý AI, brief công việc, QA, và lịch sử.

| Thư mục | Mô tả | Cách sử dụng |
|---------|--------|-------------|
| `project/tro-ly/` | **Hướng dẫn cho trợ lý AI (Antigravity)** | Chứa system prompt, cách viết prompt, quy trình làm việc |
| ↳ `SYSTEM_PROMPT.md` | Vai trò & nguyên tắc hoạt động của trợ lý | Đọc đầu mỗi phiên làm việc |
| ↳ `PROMPT_GUIDE.md` | Template viết prompt cho từng công cụ AI | Cập nhật khi học được kỹ thuật mới |
| ↳ `WORKFLOW.md` | Quy trình điều hành dự án 3 phase | Theo dõi tiến độ tổng thể |
| `project/briefs/dang-lam/` | **Brief đang thực hiện** | Mỗi task lớn tạo 1 brief ở đây |
| `project/briefs/hoan-thanh/` | **Brief đã hoàn thành** | Chuyển brief từ `dang-lam/` sang khi xong |
| `project/qa/checklist/` | **Checklist kiểm tra chất lượng** | Template QA cho video, nội dung |
| `project/qa/ket-qua/` | **Kết quả kiểm tra** | Lưu kết quả QA từng video/batch |
| `project/lich-su/` | **Lịch sử dự án** | Tracking mọi thay đổi & bài học |
| ↳ `CHANGELOG.md` | Log thay đổi quan trọng | Entry mới thêm ở đầu file |
| ↳ `SAI_LAM_VA_BAI_HOC.md` | Ghi nhận sai lầm & bài học rút ra | Mỗi sai lầm 1 entry có nguyên nhân + cách tránh |

---

### `assets/` — Tài nguyên sáng tạo

Lưu trữ mọi tài nguyên media sử dụng trong sản xuất video.

| Thư mục | Mô tả | Loại file |
|---------|--------|-----------|
| `assets/characters/` | Hình ảnh nhân vật Mèo Ú (reference, generated) | PNG, JPG, WEBP |
| `assets/thumbnails/` | Ảnh bìa/thumbnail cho video | PNG, JPG |
| `assets/music/` | Nhạc nền, sound effects | MP3, WAV |
| `assets/templates/` | Template video, overlay, text animation | PSD, AI, MP4 |

---

### `output/` — Sản phẩm đầu ra

Quản lý video theo trạng thái sản xuất.

| Thư mục | Mô tả | Quy trình |
|---------|--------|----------|
| `output/drafts/` | Video nháp, đang chỉnh sửa | Tạo video → lưu ở đây → QA check |
| `output/published/` | Video đã đăng lên TikTok | Sau khi đăng xong → chuyển sang đây |

---

*Khởi tạo: 20/03/2026*

#duanmeomap
