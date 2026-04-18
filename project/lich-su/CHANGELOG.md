# 📜 Changelog — Mèo Ú Nấu Ăn

Ghi nhận các thay đổi quan trọng trong dự án.

---

## 2026-03-21

### Đổi style nhân vật Mèo Ú — Chân chất giản dị (v2)
- **Viết lại toàn bộ** `MEO_U_CHARACTER_BIBLE.md` theo feedback user + ZK:
  - ❌ Bỏ mũ đầu bếp + khăn cổ đỏ → mèo trần tự nhiên
  - 🎨 Đổi style: 3D Pixar Chibi → **semi-realistic, warm, natural cute**
  - 🌾 Đổi bối cảnh: bếp trong nhà → **đồng quê Việt Nam** (cánh đồng lúa, bàn gỗ dưới gốc cây, bếp đất nung)
  - ✅ Giữ nguyên: siêu mập, lông cam sọc gừng, tính cách, cooking behaviors
- Cập nhật negative prompts: thêm `no clothing!, no chef hat!, no Pixar!, no anime!`
- Đồng bộ **toàn bộ 9 file** liên quan (GEMINI.md, SYSTEM_PROMPT, PROMPT_GUIDE, ANTIGRAVITY_GUIDE, prompt-writer, video-qa, tao-video, VIDEO_QA_CHECKLIST, Character Bible)
- Nguồn: feedback ảnh tham khảo từ user + ý kiến ZK ("chân chất giản dị vợ thích hơn")

### Nâng cấp nhân vật Mèo Ú — Siêu Mập (Ultra-Chubby) + Quy tắc Bảo vệ Nhân vật
- Cập nhật `MEO_U_CHARACTER_BIBLE.md`: Visual DNA siêu mập + template Veo mới + **Section 9: Quy tắc Bảo vệ Nhân vật**
- Bổ sung negative prompts: `no slim cat!, no thin waist!, no visible ribs!`
- Cập nhật vận động: bụng rung theo bước, ngồi xuống bụng tràn hai bên
- Thêm **quy tắc bảo vệ nhân vật**: agent tự sửa prompt sai → giữ bối cảnh, thay Visual DNA
- Đồng bộ **9 file** liên quan:
  - `GEMINI.md` (root) — thêm đặc điểm siêu mập + quy tắc bảo vệ
  - `project/tro-ly/SYSTEM_PROMPT.md` — thêm tóm tắt + quy tắc bảo vệ
  - `project/tro-ly/PROMPT_GUIDE.md` — thêm checklist video/ảnh + nhắc siêu mập
  - `project/tro-ly/ANTIGRAVITY_GUIDE.md` — thêm nhắc Character Bible vào KI section
  - `project/qa/checklist/VIDEO_QA_CHECKLIST.md` — nâng cấp toàn bộ, thêm kiểm tra độ mập
  - `.agents/skills/prompt-writer/SKILL.md` — thêm đặc điểm cốt lõi + quy tắc bảo vệ
  - `.agents/skills/video-qa/SKILL.md` — thêm kiểm tra độ mập + FAIL nếu gầy
  - `.agents/workflows/tao-video.md` — thêm nhắc siêu mập vào Phase 0 + Phase 5

---

## 2026-03-20

### Xây dựng hệ thống nhất quán nhân vật
- Tạo `project/nhan-vat/MEO_U_CHARACTER_BIBLE.md` — nguồn sự thật duy nhất
- Cập nhật `GEMINI.md`: thêm 6 quy tắc nhân vật + link Character Bible
- Nâng cấp skill `prompt-writer`: Bước 0 đọc Bible bắt buộc + Template 7 Lớp Veo 3.1
- Nâng cấp workflow `/tao-video`: 6 phases + Character Bible + giờ vàng
- Cập nhật `SYSTEM_PROMPT.md`: thêm section nhân vật + quy trình sản xuất mới

### Nghiên cứu chiến lược kênh TikTok AI ẩm thực
- Nhận & lưu kết quả → `docs/04_chien_luoc/xu-huong/2026-03-20_strategy-ket-qua.md`
- Hybrid Strategy: Global (ASMR, Creator Rewards $0.70/1K) + VN (lồng tiếng, TikTok Shop)
- VN KHÔNG có Creator Rewards → doanh thu view = $0
- 5 nguồn thu: Creator Rewards, TikTok Shop, Affiliate, Merch (POD), Brand Deals
- Growth roadmap 4 GĐ: 0→1K→10K→100K+
- Dự phóng: $2,410–$4,300/tháng tại 100K followers, chi phí $84–160/tháng

### Nghiên cứu thiết kế nhân vật AI cho TikTok
- Nhận & lưu kết quả → `docs/03_nhan_vat/phong-cach/2026-03-20_character-design-ket-qua.md`
- Character Bible mẫu Mèo Ú (Chef Paws): Visual DNA, Big Five, Cooking Behaviors, Negative Prompts
- Chọn phong cách: Hybrid 3D Pixar + Chibi
- Silhouette: quả lê + mũ lệch + khăn đỏ phân ranh
- Reference Sheet: Anchor Image 4 góc + 3 biểu cảm
- USP: "Con mèo ú vụng về nhất nhưng nấu ngon nhất"

### Nghiên cứu quy trình sản xuất video AI cho TikTok
- Nhận & lưu kết quả → `docs/02_ai_video/quy-trinh/2026-03-20_workflow-ket-qua.md`
- Case studies: @thatlittlepuff (33.2M), Kozwin Studios ($1.2M/28 kênh), kênh mèo AI (825K)
- Quy trình 30 phút: Script→Image→Video→Audio→Edit
- Batch production: Prompt Library + n8n automation
- TikTok algorithm 2026: Hook 3s, giờ vàng, SEO, trending sound trick

### So sánh 7 công cụ AI Video
- Nhận & lưu kết quả → `docs/02_ai_video/so-sanh-cong-cu/2026-03-20_so-sanh-ket-qua.md`
- Thu hoạch: Kling 3.0 #1 Elo (1248), Combo Workflow 4 giai đoạn, chi phí Hailuo $35 vs Sora $420
- Toolchain tối ưu: Nano Banana Pro → Kling/Hailuo → Pika 2.5 → CapCut (~$26-50/tháng)

### Nghiên cứu Google Veo 3.1
- Nhận & lưu kết quả DeepSearch → `docs/02_ai_video/gemini-veo/2026-03-20_veo-research-ket-qua.md`
- Thu hoạch: specs kỹ thuật, Kiến Trúc Prompt 7 Lớp, Ingredients to Video, pricing, chiến lược sản xuất
- Phân tích prompt viết video ban đầu của user → đánh giá 7.5/10, đề xuất cải thiện

### Thiết lập Agent Infrastructure
- Nâng cấp `SYSTEM_PROMPT.md` — hướng dẫn toàn diện cho trợ lý điều hành
- Tạo 3 Skills: `deepsearch-analyst`, `video-qa`, `prompt-writer`
- Tạo Workflow: `/tao-video` — quy trình sản xuất video 5 phase
- Cập nhật `GEMINI.md` với Brief Routing rules
- Ghi bài học về brief placement vào `SAI_LAM_VA_BAI_HOC.md`

### Nghiên cứu Antigravity IDE
- Gửi prompt DeepSearch nghiên cứu 8 chiều kích của Antigravity
- Nhận & lưu kết quả → `docs/01_prompting/deepsearch/2026-03-20_antigravity-research-ket-qua.md`
- Cập nhật `project/tro-ly/ANTIGRAVITY_GUIDE.md` với benchmark data (ARC-AGI-2, MCP Atlas, LMArena)
- Tạo `.agents/workflows/deepsearch-research.md` — workflow chuẩn cho nghiên cứu
- Tạo `GEMINI.md` (global rules) ở root dự án

### Meta-research: Kỹ thuật viết prompt cho DeepSearch
- Gửi prompt meta-research cho Google DeepSearch
- Nhận & lưu kết quả nghiên cứu → `docs/01_prompting/deepsearch/2026-03-20_meta-research-ket-qua.md`
- Rút trích Khung 4 Phần + 4 template + checklist → cập nhật `project/tro-ly/PROMPT_GUIDE.md`

### Khởi tạo dự án
- Tạo cấu trúc folder dự án đầy đủ
- Tạo README.md tổng quan
- Thiết lập hệ thống quản lý: briefs, QA, lịch sử
- Tạo hướng dẫn cho trợ lý AI (SYSTEM_PROMPT, PROMPT_GUIDE, WORKFLOW)
