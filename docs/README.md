# 📚 Docs — Tổng Quan Nghiên Cứu Dự Án Mèo Ú Nấu Ăn

> **Cập nhật**: 2026-03-20
> **Tổng số phiên nghiên cứu**: 5 phiên DeepSearch + 2 phiên meta-research
> **Trạng thái**: ✅ Giai đoạn nghiên cứu nền tảng hoàn tất

---

## 📁 Cấu Trúc Folder

```
docs/
├── 01_prompting/          ← Kỹ thuật viết prompt
│   └── deepsearch/        ← Prompt & kết quả DeepSearch
├── 02_ai_video/           ← Công nghệ tạo video AI
│   ├── gemini-veo/        ← Google Veo 3.1 chuyên sâu
│   ├── so-sanh-cong-cu/   ← So sánh 7 công cụ AI video
│   └── quy-trinh/         ← Quy trình sản xuất & case studies
├── 03_nhan_vat/           ← Thiết kế nhân vật Mèo Ú
│   ├── phong-cach/        ← Character Bible, visual style, reference sheet
│   ├── tham-khao/         ← (Data nằm trong phong-cach)
│   └── tinh-cach/         ← (Data nằm trong phong-cach)
└── 04_chien_luoc/         ← Chiến lược kinh doanh & tăng trưởng
    ├── xu-huong/          ← Hybrid Strategy, monetization, roadmap
    ├── doi-thu/           ← (Nghiên cứu bổ sung khi cần)
    ├── lich-dang/         ← (Data giờ vàng nằm trong 02/quy-trinh)
    └── thuat-toan/        ← (Data thuật toán nằm trong 02/quy-trinh)
```

---

## 📋 Danh Sách File Nghiên Cứu

### 01 — Prompting & Meta-Research

| File | Nội dung |
|------|----------|
| [antigravity-research-ket-qua.md](01_prompting/deepsearch/2026-03-20_antigravity-research-ket-qua.md) | Kiến trúc Antigravity IDE, model routing, KI system |
| [meta-research-ket-qua.md](01_prompting/deepsearch/2026-03-20_meta-research-ket-qua.md) | Khung 4 Phần viết prompt, 4 templates DeepSearch |

---

### 02 — AI Video (3 phiên)

| File | Nội dung chính | Thu hoạch cốt lõi |
|------|---------------|-------------------|
| [veo-research-ket-qua.md](02_ai_video/gemini-veo/2026-03-20_veo-research-ket-qua.md) | Google Veo 3.1 specs | 4K native, Ingredients to Video (4 ref images), 7-Layer Prompt, max 8s/clip, $0.15-0.40/s |
| [so-sanh-ket-qua.md](02_ai_video/so-sanh-cong-cu/2026-03-20_so-sanh-ket-qua.md) | So sánh 7 công cụ | Kling 3.0 #1 Elo (1248), Combo Workflow 4 GĐ, Hailuo rẻ nhất ($35 vs Sora $420) |
| [workflow-ket-qua.md](02_ai_video/quy-trinh/2026-03-20_workflow-ket-qua.md) | Quy trình + case studies | 30 phút/video, batch production, @thatlittlepuff 33.2M, TikTok algorithm 2026 |

---

### 03 — Nhân Vật (1 phiên)

| File | Nội dung chính | Thu hoạch cốt lõi |
|------|---------------|-------------------|
| [character-design-ket-qua.md](03_nhan_vat/phong-cach/2026-03-20_character-design-ket-qua.md) | Character Bible Mèo Ú | Hybrid 3D Pixar + Chibi, silhouette quả lê, mũ lệch, Big Five personality, Reference Sheet prompt, LoRA training |

---

### 04 — Chiến Lược (1 phiên)

| File | Nội dung chính | Thu hoạch cốt lõi |
|------|---------------|-------------------|
| [strategy-ket-qua.md](04_chien_luoc/xu-huong/2026-03-20_strategy-ket-qua.md) | Chiến lược toàn diện | Hybrid 2 tài khoản (Global ASMR + VN lồng tiếng), 5 nguồn thu, $2.4K-$4.3K/tháng tại 100K followers |

---

## 🎯 Kết Luận Chiến Lược Từ Nghiên Cứu

### Toolchain sản xuất:
```
Nano Banana Pro (ảnh) → Kling 3.0 / Hailuo 2.3 (video) → Pika 2.5 (lip-sync) → CapCut (hậu kỳ)
```

### Nhân vật — Mèo Ú (Chef Paws):
- **Phong cách**: Hybrid 3D Pixar + Chibi
- **Màu**: `vibrant marigold orange` + `creamy vanilla white`
- **Trang phục**: Mũ đầu bếp mini (lệch 45°) + Khăn đỏ thắm
- **USP**: "Con mèo ú vụng về nhất nhưng nấu ngon nhất"

### Chiến lược kênh:
- **Global**: ASMR không lời → Creator Rewards ($0.70/1K views)
- **Việt Nam**: Lồng tiếng hài → TikTok Shop + Affiliate
- **Chi phí**: $84-160/tháng (hoặc <$20 dùng free tiers)
- **Mục tiêu doanh thu**: $2,410-$4,300/tháng tại 100K followers

### Quy trình sản xuất:
- **30 phút/video**: Script (3') → Image (5') → Animate (7') → Audio (5') → Edit (10')
- **Batch**: 10-30 video/tuần với Prompt Library + CapCut Template

---

## ⏭️ Bước Tiếp Theo

- [ ] Tạo Master Image Mèo Ú (Nano Banana Pro)
- [ ] Tạo Reference Sheet (4 góc + 3 biểu cảm)
- [ ] Test 3 video đầu tiên bằng Hailuo 2.3
- [ ] Thiết lập 2 tài khoản TikTok (Global + VN)
- [ ] Xây Prompt Library trong Google Sheets
