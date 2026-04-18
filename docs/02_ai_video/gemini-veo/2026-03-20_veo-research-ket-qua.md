# Nghiên Cứu Chuyên Sâu: Google Veo 3.1 — Sản Xuất Video AI Cho TikTok

> **Ngày**: 2026-03-20
> **Nguồn**: Google DeepSearch
> **Brief**: `project/briefs/dang-lam/2026-03-20_ai-video-research.md` (Phiên 1)
> **Trạng thái**: ✅ Hoàn thành

---

## Tóm Tắt Điều Hành

Veo 3.1 (ra mắt 13/01/2026) là công cụ tạo video AI mạnh nhất hiện tại cho sản xuất TikTok. Ba trụ cột: **4K native 9:16**, **âm thanh đồng bộ tích hợp**, và **Ingredients to Video** (giữ nhân vật nhất quán). Giới hạn chính: max 8s/clip, lỗi tay/ngón, không render được chữ, lời thoại chỉ 25% thành công.

---

## 1. Thông Số Kỹ Thuật

### Bảng so sánh các phiên bản:

| Tiêu chí | Veo 2 (2024) | Veo 3 (2025) | Veo 3.1 Fast | Veo 3.1 Quality |
|----------|-------------|-------------|-------------|----------------|
| **Độ phân giải** | Lên tới 4K | 1080p | 1080p | **4K (3840×2160)** |
| **Native 9:16** | ❌ Phải crop | ❌ Phải crop | ✅ | ✅ |
| **Âm thanh** | ❌ Câm | SFX cơ bản | Đối thoại + SFX | **Lip-sync 48kHz** |
| **Character consistency** | Kém | Trung bình | Tốt | **Xuất sắc (4 ảnh ref)** |
| **Render time (8s clip)** | 60-90s | 150-180s | **45-73s** | 160-180s |
| **FPS** | 24 | 30 | 24/30 | **Lên tới 60** |
| **Thời lượng/clip** | — | — | Max 8s | Max 8s |

### 💡 Insights:
- **Video Extension**: Nối clips lên tới **148 giây** (2.5 phút) bằng cách lấy 24 frame cuối làm anchor
- **4K thật**: Không phải upscale — AI tái tạo chi tiết vi mô (lông mèo, kết cấu vải)

---

## 2. Character Consistency — ĐẶC BIỆT QUAN TRỌNG

### Tính năng "Ingredients to Video":
- Upload tối đa **4 ảnh tham chiếu** (PNG/JPEG/WEBP, ≤50MB)
- AI trích xuất **identity vector**: xương hàm, tỷ lệ mắt, họa tiết trang phục
- Vector này **ép buộc** AI giữ nhân vật nhất quán xuyên suốt video

### Quy trình 3 bước giữ Mèo Ú nhất quán:

```
Bước 1: Tạo Master Image
  → Dùng Nano Banana Pro / Gemini 3 Pro Image
  → Prompt chi tiết: "A 3D Pixar-style chubby orange cat..."
  → Bước này quyết định 90% tính nhất quán

Bước 2: Upscale hình ảnh
  → Dùng Topaz Gigapixel AI
  → Khử nhiễu + tăng độ sắc nét

Bước 3: Tích hợp vào Veo 3.1
  → Upload Master Image làm "Ingredient"
  → Prompt CHỈ mô tả hành động + bối cảnh
  → KHÔNG lặp lại mô tả ngoại hình
```

### Start & End Frame Control:
- Upload 2 ảnh (đầu + cuối) → Veo tự nội suy chuyển động giữa 2 điểm
- Triệt tiêu rủi ro nhân vật đi sai hướng

### Seed Parameter:
- Dải: -1 đến 999999999999999
- Dùng để **re-render cùng cảnh** khi cần sửa lỗi nhỏ
- KHÔNG dùng để giữ nhân vật giữa các cảnh khác nhau

### Character ID:
- ⚠️ **Chưa xác nhận** Veo 3.1 có Character ID nội bộ (tính đến Q1/2026)
- Giải pháp bên thứ ba: **Higgsfield AI (Soul ID)**, **Ulazai (Character Lock)**

### Giới hạn:
- Lỗi ở chuyển động xoay 360°, ống kính fisheye
- Chi tiết nhỏ (logo, vết sẹo) có thể biến mất ở 1-2 frame

---

## 3. Prompt Engineering — Kiến Trúc 7 Lớp

### Công thức tối ưu (80-150 từ, thứ tự ưu tiên giảm dần):

| Lớp | Nội dung | Ví dụ |
|-----|----------|-------|
| 1️⃣ **Camera & Lens** | Cỡ cảnh + chuyển động | `Medium shot, slow dolly in` |
| 2️⃣ **Subject** | Chủ thể (ngắn gọn nếu có ref image) | `The orange cat from reference` |
| 3️⃣ **Action & Physics** | MỘT hành động cụ thể | `shuffling with hunched shoulders` |
| 4️⃣ **Environment** | Bối cảnh | `in a dense misty pine forest` |
| 5️⃣ **Lighting** | Kỹ thuật ánh sáng | `Golden hour, Rembrandt lighting` |
| 6️⃣ **Style & Texture** | Phong cách | `3D Pixar-style animation` |
| 7️⃣ **Audio** | Âm thanh | `Audio: sizzle of pan, birds chirping` |

### Quy tắc vàng:
- **1 hành động/clip** — nhiều hành động = sập thuật toán
- **Dùng JSON format** giảm 70% kết quả ngẫu nhiên: `{"camera":"...", "subject":"...", "audio":"..."}`
- **Negative prompts PHẢI có**: `(no subtitles!, no text overlays!)`
- **Dialogue format**: `Character says: "Nội dung"` (KHÔNG dùng ngoặc kép thường)
- **Phonetic spelling** cho từ khó: `"foh-fur"` thay vì `"fofr"`

---

## 4. Chi Phí & Truy Cập

### Google Flow (No-code, trên trình duyệt):

| Gói | Giá/tháng | Credits | Veo Fast | Veo Quality | Ghi chú |
|-----|----------|---------|----------|------------|---------|
| **AI Pro** | $19.99 | 1,000 | 50 video | 10 video | 720p, có watermark |
| **AI Ultra** | $249.99 | 25,000 | ∞ (miễn phí) | 250 video | 1080p, không watermark |

### API (Pay-per-second):

| Model | Giá/giây | Clip 8s | Ghi chú |
|-------|---------|---------|---------|
| **Veo 3.1 Standard** | $0.40 | **$3.20** (~80K VNĐ) | 4K, chất lượng cao |
| **Veo 3.1 Fast** | $0.15 | **$1.20** (~30K VNĐ) | 1080p, nhanh |

### 💡 Breakeven Analysis:
- **< 7 video Fast/tháng** → dùng API hoặc gói Plus ($7.99)
- **> 47 video Standard/tháng** → gói Ultra ($249.99) rẻ hơn API

### Rate Limits (API):
- 250 RPD (requests/day), 20-50 RPM
- Vượt limit → dùng API aggregator (APIYI, GlobalGPT)

---

## 5. Kinh Nghiệm Thực Chiến

### Định luật "Cắt Nhỏ 8 Giây":
```
❌ SAI: Paste kịch bản 60s vào 1 prompt
✅ ĐÚNG: Chia thành 8-12 shots × 8s → render riêng → ghép bằng CapCut/DaVinci
```

### Công thức "Poor Cat Story" (viral TikTok):
```
Hook (mèo buồn dưới mưa)
  → Conflict (bị cười nhạo)
    → Climax (làm việc vất vả)
      → End (trở nên giàu có)
```

### Format viral:
- **Selfie Vlogger**: `"A selfie video of... holds camera at arm's length"`
- **Street Interview**: Phải ghi rõ vị trí đứng, tránh "ảo giác vị trí"

### Tích hợp YouTube Shorts:
- **Add Motion**: Chuyển giao chuyển động từ video khác sang ảnh tĩnh
- **Stylize**: Chuyển đổi phong cách (pop-art, watercolor, origami)

---

## 6. Giới Hạn & Điểm Yếu — PHẢI NHỚ

| Vấn đề | Mức độ | Giải pháp |
|--------|--------|-----------|
| **Chất lỏng/vật lý** | 🔴 Nghiêm trọng | Tránh cảnh đổ nước, sóng |
| **Tay/ngón tay** | 🔴 Nghiêm trọng | Góc quay từ ngực lên, khuất tay |
| **Text/chữ** | 🔴 Nghiêm trọng | `(no text)` + chèn chữ hậu kỳ |
| **Lời thoại** | 🟡 Trung bình (25% OK) | Tắt dialogue Veo → dùng ElevenLabs |
| **Subtitle tự chèn** | 🟡 Trung bình | `(no subtitles!, no text overlays!)` |
| **Anime 2D** | 🟡 Bị lai 2.5D | Cần keyword rào chắn cẩn thận |

---

## 7. Dự Báo: Veo 4

- **Khi nào**: Chưa xác nhận — dự kiến Google I/O 2026
- **Kiến trúc mới**: "World Simulator Engine" — hiểu vật lý hoàn toàn
- **Tính năng kỳ vọng**: Character ID nội bộ, clip tới 60s, sửa lỗi chất lỏng

---

## 8. Áp Dụng Cho Dự Án Mèo Ú

### Chiến lược sản xuất đề xuất:

| Bước | Công cụ | Chi phí |
|------|---------|---------|
| Tạo Master Image Mèo Ú | Nano Banana Pro | (miễn phí/rẻ) |
| Upscale | Topaz Gigapixel | $99 (1 lần) |
| Test nhanh các cảnh | Veo 3.1 Fast | $0.15/s |
| Render final hero shots | Veo 3.1 Standard | $0.40/s |
| Lời thoại/voice-over | ElevenLabs | ~$5-22/tháng |
| Ghép + chữ + nhạc | CapCut | Miễn phí |

### Chi phí ước tính 1 video (60s, 10 shots):
- Fast draft: 10 × $1.20 = **$12** + vài lần thử = ~**$20-30**
- Quality final: 10 × $3.20 = **$32** + thử = ~**$50-70**
- **Gói Pro ($19.99)**: Chỉ đủ 10 video Quality/tháng → hạn chế
- **Gói Ultra ($249.99)**: 250 video Quality + Fast ∞ → phù hợp nếu scale
