---
name: prompt-writer
description: Viết prompt theo Khung 4 Phần cho DeepSearch, Gemini Video, và Image Generation
---

# Goal

Viết prompt chất lượng cao cho các công cụ AI (DeepSearch, Gemini Video/Veo 3.1, Image Gen) theo đúng Khung 4 Phần. Khi viết prompt video/ảnh Mèo Ú → **BẮT BUỘC đọc Character Bible trước**.

# Instructions

## Bước 0 — Đọc Character Bible (BẮT BUỘC cho Video/Ảnh)

Khi viết prompt cho video hoặc hình ảnh Mèo Ú:
1. **PHẢI đọc** `project/nhan-vat/MEO_U_CHARACTER_BIBLE.md` TRƯỚC
2. Copy nguyên văn "Visual DNA" từ Character Bible — KHÔNG tự sáng tạo
3. Copy nguyên văn "Negative Prompts" — KHÔNG bỏ sót
4. Chỉ thay đổi: Action, Food, Camera, Audio

### ⚠️ Đặc điểm cốt lõi của Mèo Ú (phải luôn đúng):
- **SIÊU MẬP**: `extremely fat, ultra-chubby, massive perfectly round ball-shaped body`
- **Bụng khổng lồ** gần chạm đất, chân ngắn cũn cỡn gần bị bụng che
- **Má phính, cằm đôi**, mặt tròn to
- **Trang phục**: ❌ KHÔNG MŨ, KHÔNG KHĂN — mèo trần tự nhiên
- **Style**: semi-realistic, warm, chân chất (KHÔNG Pixar, KHÔNG anime)
- **Bối cảnh**: Đồng quê VN, bàn gỗ dưới gốc cây, bếp đất nung
- Negative: `no skinny body!, no slim cat!, no clothing!, no chef hat!, no Pixar!`
- **KHÔNG BAO GIỜ** vẽ mèo gầy hoặc mặc đồ — Mèo Ú là mèo siêu béo trần tự nhiên

## Bước 1 — Xác định công cụ đích

- **DeepSearch**: Nghiên cứu → Khung 4 Phần
- **Veo 3.1**: Video Mèo Ú → Template 7 Lớp + Character Bible
- **Image Gen** (Nano Banana Pro / Midjourney): Ảnh tĩnh → Character Bible

## Bước 2 — Viết prompt

### Cho DeepSearch: Khung 4 Phần
```
1. VAI TRÒ (Persona)      → "Đóng vai [chuyên gia cụ thể]"
2. NHIỆM VỤ (Task)        → Động từ mạnh: Phân tích, So sánh, Xây dựng
3. RÀNG BUỘC (Constraints) → Cấm nguồn kém, cấm ước tính, format yêu cầu
4. ĐẦU RA (Output Format)  → Bảng, Markdown, tóm tắt max N từ
```

### Cho Veo 3.1: Template 7 Lớp
```
[1. CAMERA]      Cỡ cảnh + chuyển động (VD: Medium shot, slow dolly in)
[2. SUBJECT]     Visual DNA từ Character Bible (nguyên văn) — mèo trần, không mũ/khăn
                 HOẶC "The extremely fat orange tabby cat from reference" (nếu có ref image)
[3. ACTION]      MỘT hành động duy nhất (VD: carefully slicing onions)
[4. ENVIRONMENT] outdoor Vietnamese countryside, wooden table under tree, green rice fields
[5. LIGHTING]    warm natural golden sunlight
[6. STYLE]       semi-realistic, warm, natural cute
[7. AUDIO]       Audio: sizzling of pan, gentle chopping sounds

NEGATIVE: (paste từ Character Bible)
```

### Cho Reference Sheet (Image Gen):
```
Create a professional character reference sheet on plain white background.
Two horizontal rows on same canvas.
Top: 4 full-body (Front, Left profile, Three-quarter, Back)
Bottom: 3 close-ups (Neutral, Focused tongue out, Ecstatic cheeks puffed)
Character: [PASTE VISUAL DNA]
Style: 3D Pixar animation, chibi proportions.
Neutral studio lighting. No dramatic shadows.
```

## Bước 3 — Checklist

### DeepSearch:
- [ ] Có VAI TRÒ cụ thể?
- [ ] Dùng ĐỘNG TỪ MẠNH?
- [ ] Có RÀNG BUỘC TIÊU CỰC?
- [ ] Có ĐỊNH DẠNG ĐẦU RA?
- [ ] Có "ghi 'Dữ liệu không khả dụng'"?

### Video/Ảnh Mèo Ú:
- [ ] Đã đọc Character Bible?
- [ ] Visual DNA đúng nguyên văn?
- [ ] Negative prompts có đầy đủ?
- [ ] Chỉ MỘT hành động/clip?
- [ ] Max 80-150 từ?
- [ ] Có Audio layer?

## Bước 4 — Lưu prompt
- Prompt nghiên cứu → `project/briefs/dang-lam/YYYY-MM-DD_[ten]-prompt.md`
- Prompt video → trong brief video tương ứng

# Constraints

- **Character Bible là BẮT BUỘC** — KHÔNG viết prompt video/ảnh mà không đọc
- PHẢI có đủ 4 phần (DeepSearch) hoặc 7 lớp (Veo)
- PHẢI có negative prompts trong mọi prompt video/ảnh
- **1 hành động/clip** — nhiều hành động = AI sập
- KHÔNG tự sáng tạo mô tả nhân vật — chỉ dùng Visual DNA
- KHÔNG viết prompt chung chung kiểu "Hãy nói cho tôi về..."
- Prompt video bằng **tiếng Anh** (Veo 3.1 nhận tiếng Anh)

### 🛡️ Bảo vệ nhân vật — Tự điều chỉnh prompt user:
- Nếu user gửi prompt mô tả mèo **không khớp** Character Bible (gầy, màu sai, thiếu mũ/khăn, không đủ mập...) → **PHẢI tự sửa** phần mô tả nhân vật cho đúng Visual DNA
- **GIỮ nguyên** bối cảnh, hành động, món ăn của user — chỉ thay phần mô tả mèo
- **Thông báo** cho user biết đã điều chỉnh những gì
