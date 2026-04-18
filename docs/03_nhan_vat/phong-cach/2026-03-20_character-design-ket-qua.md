# Thiết Kế Nhân Vật AI Cho TikTok — Character Bible & Reference System

> **Ngày**: 2026-03-20
> **Nguồn**: Google DeepSearch
> **Brief**: `project/briefs/dang-lam/2026-03-20_nhanvat-chienluoc-research.md` (Phiên 1)
> **Trạng thái**: ✅ Hoàn thành

---

## Tóm Tắt Điều Hành

Phong cách tối ưu: **Hybrid 3D Pixar + Chibi** (nhất quán AI cao nhất + engagement cao nhất). Character Bible phải là "văn bản cho máy đọc" — không phải bản vẽ cho người xem. Mèo Ú nên kết hợp ASMR + mini-narrative + **sự vụng về có chủ đích** để khác biệt.

---

## 1. Character Bible — "Mèo Ú" (Chef Paws)

### Cấu trúc 5 lớp của AI Character Bible:

| Lớp | Nội dung | Ví dụ Mèo Ú |
|-----|----------|-------------|
| **BOL** (Base Operating Layer) | Giới hạn vật lý, negative prompts | KHÔNG: bàn tay người, mèo gầy, quần áo người |
| **PIL** (Persona Identity Layer) | Vai trò, sứ mệnh, bối cảnh | Đầu bếp nghiệp dư đam mê, vụng về nhưng ngon |
| **Visual DNA** | Mô tả ngoại hình cực chi tiết | Xem bên dưới |
| **Personality Framework** | Hành vi quan sát được | Big Five + Cooking Behaviors |
| **Environmental Anchors** | Bối cảnh, ánh sáng, bảng màu không gian | Bếp mộc mạc, ánh sáng ấm |

### 📋 Character Bible Mẫu — MÈO Ú:

```
ĐỊNH DANH: Mèo Ú (Chef Paws)
PHÂN LOẠI: Mèo mướp Anh lông ngắn, nhân hóa nhẹ

TỶ LỆ: Thể khối tròn trịa cực đại (extreme spherical chubby),
        bụng phệ chạm sàn, không đường nét góc cạnh

VẬN ĐỘNG: 4 chân bình thường, đứng 2 chân SAU khi nấu ăn

MÀU SẮC:
  - Lông: "vibrant marigold orange fur" + "subtle ginger stripes"
  - Bụng/ngực/mõm: "creamy vanilla white belly"
  - Mắt: [cần xác định — đề xuất: amber/vàng hổ phách]

TRANG PHỤC (chỉ 2 món — tối giản):
  1. Mũ đầu bếp mini trắng, nghiêng 45° bên tai phải
  2. Khăn quàng cổ đầu bếp đỏ thắm (crimson red), thắt nơ trước ngực

TÍNH CÁCH (Big Five):
  - Cởi mở: CAO
  - Tận tâm: THẤP (hay làm đổ đồ)
  - Đồng thuận: CAO (luôn vui vẻ)

COOKING BEHAVIORS:
  - Cắt thái → thè lưỡi tập trung
  - Nếm thử → mắt nhắm tịt hình trăng khuyết, má phồng to
  - Chờ đợi → ngủ gật bên bếp
  - Lỗi nấu → tai cụp, rũ rượi (KHÔNG tức giận)
  - Hay nếm vụng nguyên liệu trên thớt

❌ NEGATIVE PROMPTS (BẮT BUỘC):
  - NO human hands/fingers
  - NO creepy realistic cat eyes
  - NO skinny body
  - NO human clothing (t-shirts, pants)
  - NO perfectly upright human posture
```

---

## 2. Phong Cách Hình Ảnh — So Sánh 5 Styles

| Phong cách | AI Consistency | Engagement | Phù hợp Mèo Ú? |
|-----------|---------------|------------|-----------------|
| **3D Pixar** | ⭐⭐⭐⭐⭐ Cao nhất | ⭐⭐⭐⭐⭐ Đứng đầu | ✅ **CHỌN** |
| **Anime 2D** | ⭐⭐⭐⭐ Tốt (lỗi flickering góc xoay) | ⭐⭐⭐⭐⭐ Gen Z/Alpha | ⚠️ Backup |
| **Chibi** | ⭐⭐⭐ TB (lỗi chuyển động) | ⭐⭐⭐⭐⭐ Kawaii niche | ✅ **KẾT HỢP** |
| **Stop-motion** | ⭐⭐ Thấp (flickering) | ⭐⭐⭐ Độc lạ | ❌ Khó sản xuất hàng loạt |
| **Realistic** | ⭐⭐ Khó giữ ổn định | ⭐⭐ Uncanny valley | ❌ |

### 🎯 Khuyến nghị: **Hybrid 3D Pixar + Chibi**
- 3D Pixar → render ánh sáng/vật liệu tốt → food porn đẹp
- Chibi → đầu to, thân mũm mĩm → cute tối đa
- AI giữ nhất quán tốt nhất với 3D

---

## 3. Đặc Điểm Nhận Dạng — Silhouette Test

### Phân tích mascot thành công:

| Nhân vật | Silhouette | Bảng màu | Phụ kiện | Bí quyết |
|----------|-----------|----------|----------|---------|
| **Pusheen** | Oval "ổ bánh mì" | Xám tro | Không cố định | Tối giản, vô hại |
| **Garfield** | Bụng phệ, bọng mắt to | Cam đậm + đen | Khay Lasagna | Hài hước yếm thế |
| **Hello Kitty** | Đầu oval + **nơ lệch** | Trắng + đỏ | Nơ đỏ tai trái | **Bất đối xứng** → ghi nhớ tức thì |
| **@thatlittlepuff** | Mèo thật | Trắng xám | "Tay mèo giả" | Tốc độ + ASMR |

### Chiến lược Silhouette cho Mèo Ú:
- Hình khối **quả lê** (nặng phần bụng)
- Mũ đầu bếp **lệch 1 bên** (bất đối xứng như Hello Kitty)
- Khăn đỏ **tạo đường phân ranh** đầu-thân (giúp AI nhận diện khuôn mặt)

### Bảng màu — Token hóa cho AI:
```
❌ SAI:  "orange cat"  → AI trả 10 sắc cam khác nhau
✅ ĐÚNG: "vibrant marigold orange fur"  → khóa chặt 1 sắc
✅ ĐÚNG: "creamy vanilla white belly"   → không thay đổi
✅ ĐÚNG: "crimson red chef neckerchief" → tương phản cam
```

---

## 4. Food Porn Techniques — Prompt Engineering Ẩm Thực

### Phân bổ khung hình: 50% nhân vật cute + 50% món ăn hấp dẫn

### Kỹ thuật ánh sáng:
```
❌ flat lighting → thức ăn trông nhạt
✅ warm dramatic backlighting → viền sáng trên thịt/khói
✅ soft diffused morning light from window → bóng đổ êm
```

### Từ khóa "thèm ăn" cho AI:
```
Nước sốt:  "glistening rich sauce"
Phô mai:   "slowly melting cheese oozing over the edges"
Khói:      "golden saffron-infused steam swirling"
Bánh mì:   "crispy golden crust with fine flour dusting"
Đồ uống:   "condensation droplets dripping down frosted glass"
```

### Biểu cảm Mèo Ú theo giai đoạn nấu:

| Giai đoạn | Prompt biểu cảm |
|-----------|-----------------|
| **Cắt thái** | `focused narrowed eyes, tongue slightly sticking out` |
| **Đảo/nêm** | `eyes wide with anticipation, watching food intently` |
| **Thưởng thức** | `eyes closed tightly in pure delight, cheeks puffed, blissful smile` |

---

## 5. Reference Sheet — Kỹ Thuật Anchor Image

### Prompt tạo Reference Sheet chuẩn:

```
Create a professional character reference sheet on plain white background.
Arrange in two horizontal rows on the same canvas.

Top row: 4 full-body poses
  - Front view, Left profile, Three-quarter view, Back view
  - Relaxed A-pose, neutral studio lighting

Bottom row: 3 close-up portraits
  - Neutral expression, Focused (tongue out), Ecstatic (eyes closed, cheeks puffed)

Character: [DÁN CHARACTER BIBLE VÀO ĐÂY]

Maintain identical proportions, bone structure, and lighting across all panels.
No dramatic shadows. No background elements.
Style: 3D Pixar animation, chibi proportions.
```

### Quy trình sử dụng:

```
1. Tạo Anchor Image (1 ảnh chứa tất cả góc nhìn)
2. Crop từng frame riêng
3. Upload vào Kling/Hailuo làm Image Reference (strength = MAX)
4. Prompt video CHỈ mô tả hành động, KHÔNG mô tả ngoại hình
```

### LoRA Training (giải pháp dài hạn):
- 15-30 ảnh đa góc từ Character Sheet
- Độ phân giải 512px hoặc 1024px
- Batch size = 2 (tránh overfitting)
- → Nhân vật nhất quán ~100% trong mọi tình huống

---

## 6. Chiến Lược Khác Biệt Cho Mèo Ú

### Phân tích: Mèo Ú vs hàng ngàn kênh AI Cat Chef

| Yếu tố | Kênh AI Cat Chef phổ biến | Mèo Ú (đề xuất) |
|---------|--------------------------|-----------------|
| Âm thanh | ASMR im lặng | ASMR + **mini-narrative** |
| Tính cách | Robot hoàn hảo | **Vụng về có chủ đích** (làm rơi, ngủ gật) |
| Góc máy | Chỉ chính diện | **POV/Selfie** (Mèo Ú nhìn camera) |
| Cốt truyện | Không có | **Mini-drama** nhỏ mỗi video |
| Tương tác | Không | Mèo Ú "nói chuyện" với khán giả |

### 💡 USP (Unique Selling Point) đề xuất:
> **"Con mèo ú vụng về nhất TikTok nhưng nấu ngon nhất"**
> → Vụng về (comedy) + Ngon (food porn) + Nhất quán (trust) + ASMR (healing)
