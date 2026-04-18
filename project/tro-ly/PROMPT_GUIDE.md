# 📝 Hướng dẫn Viết Prompt — Dự án Mèo Ú Nấu Ăn

> Cập nhật: 2026-03-20 (dựa trên meta-research DeepSearch)

---

## 🏗️ Khung 4 Phần Tiêu Chuẩn (Bắt buộc mọi prompt)

Mọi prompt cho DeepSearch **PHẢI** có đủ 4 phần:

```
1. VAI TRÒ (Persona)     → "Đóng vai [chuyên gia cụ thể]"
2. NHIỆM VỤ (Task)       → Động từ mạnh: "Phân tích", "So sánh", "Xây dựng"
3. RÀNG BUỘC (Constraints)→ Giới hạn nguồn, cấm ước tính, format yêu cầu
4. ĐẦU RA (Output Format) → Bảng, Markdown, tóm tắt max N từ
```

---

## 📋 Template Prompt cho DeepSearch

### Template Cơ Bản
```
Đóng vai một [VAI TRÒ CHUYÊN GIA].

Nhiệm vụ: [ĐỘNG TỪ MẠNH] + [CHỦ ĐỀ CỤ THỂ].

Ràng buộc:
- [Nguồn dữ liệu cho phép/cấm]
- [Phạm vi thời gian]
- Nếu không tìm thấy dữ liệu, ghi rõ "Dữ liệu không khả dụng"
- Tuyệt đối không ước tính hoặc bịa số liệu

Trình bày kết quả dưới dạng [ĐỊNH DẠNG CỤ THỂ] với trích dẫn nguồn.
```

### Template So Sánh (Criteria-First)
```
Đóng vai một [VAI TRÒ].

Nghiên cứu [A] và [B]. Trước khi viết báo cáo:
1. Tự định danh 5 thông số quan trọng nhất mà chuyên gia dùng để đánh giá
2. Xây dựng bảng ma trận so sánh dựa trên đúng 5 thông số đó
3. Đưa ra khuyến nghị kèm lý do

Ràng buộc: [...]
```

### Template Nghiên Cứu Đa Phiên (cho chủ đề lớn)
```
Phiên 1: "Phân tích tổng quan về [khía cạnh A] của [chủ đề]"
Phiên 2: "Phân tích chuyên sâu về [khía cạnh B] của [chủ đề]"
Phiên 3: "Phân tích chuyên sâu về [khía cạnh C] của [chủ đề]"
Phiên N: "Tổng hợp các báo cáo sau thành tài liệu thống nhất: [paste kết quả 1-3]"
```

---

## 🎯 Template Cho Dự Án Mèo Ú Nấu Ăn

### ⚠️ Đặc điểm nhân vật cốt lõi (BẮT BUỘC nhớ):
- Mèo Ú = **SIÊU MẬP** (extremely fat, ultra-chubby)
- Bụng khổng lồ gần chạm đất, chân ngắn cũn cỡn, má phính cằm đôi
- ❌ KHÔNG MŨ, KHÔNG KHĂN — mèo trần tự nhiên, chân chất giản dị
- Style: semi-realistic, warm (KHÔNG Pixar, KHÔNG anime)
- Bối cảnh: Đồng quê VN, bàn gỗ dưới gốc cây, bếp đất nung
- **NGUỒN SỰ THẬT**: `project/nhan-vat/MEO_U_CHARACTER_BIBLE.md`

### Nghiên cứu AI Video
```
Đóng vai một chuyên gia sản xuất nội dung AI video.

Phân tích toàn diện về [công cụ/kỹ thuật cụ thể] trong việc tạo video
AI nhân vật hoạt hình (character animation) cho nền tảng TikTok.

Ràng buộc:
- Tập trung vào khả năng tạo nhân vật nhất quán qua nhiều video
- Bao gồm ví dụ thực tế từ các creator đã thành công
- Nếu không có dữ liệu, ghi "Dữ liệu không khả dụng"
- Ưu tiên thông tin từ sau tháng 1/2026

Trình bày: Bảng so sánh tính năng, ưu/nhược điểm thực tế, và workflow đề xuất.
```

### Nghiên cứu TikTok Algorithm
```
Đóng vai một chuyên gia phân tích thuật toán mạng xã hội.

Nghiên cứu chuyên sâu cơ chế phân phối video của TikTok trong năm 2025-2026,
đặc biệt cho niche nội dung AI-generated và cooking/pet content.

Ràng buộc:
- Chỉ sử dụng dữ liệu từ các nghiên cứu, case study có dẫn chứng
- Bỏ qua các bài "hack thuật toán" không có cơ sở
- Phân biệt rõ giữa dữ kiện đã xác minh và suy đoán

Đầu ra: Bảng các yếu tố ranking, chiến lược đăng bài tối ưu, và
các ví dụ kênh thành công trong niche tương tự.
```

---

## ⚠️ Checklist Trước Khi Gửi Prompt

### DeepSearch:
- [ ] Có chỉ định VAI TRÒ cụ thể chưa?
- [ ] Dùng ĐỘNG TỪ MẠNH chưa? (Phân tích, So sánh, Xây dựng...)
- [ ] Có RÀNG BUỘC TIÊU CỰC chưa? (Cấm nguồn nào, cấm ước tính)
- [ ] Có ĐỊNH DẠNG ĐẦU RA rõ ràng chưa?
- [ ] Chủ đề có quá rộng không? → Nếu rộng, chia thành nhiều phiên
- [ ] Đã thêm "ghi 'Dữ liệu không khả dụng' nếu không tìm thấy" chưa?

### Video/Ảnh Mèo Ú:
- [ ] Đã đọc Character Bible (`project/nhan-vat/MEO_U_CHARACTER_BIBLE.md`)?
- [ ] Visual DNA đúng nguyên văn?
- [ ] Mèo Ú có đủ SIÊU MẬP (ultra-chubby, bụng khổng lồ, chân ngắn cũn)?
- [ ] Mèo trần tự nhiên (không mũ, không khăn, không đồ)?
- [ ] Style semi-realistic (không Pixar, không anime)?
- [ ] Negative prompts có đầy đủ (bao gồm `no clothing!, no chef hat!, no Pixar!`)?
- [ ] Chỉ MỘT hành động/clip?
- [ ] Max 80-150 từ?
- [ ] Có Audio layer?

---

## 🔑 Quy Tắc Vàng

1. **Review Edit Plan** trước khi nhấn "Start Research" — đây là điểm can thiệp mạnh nhất
2. **Phân rã đa phiên** cho chủ đề >5 khía cạnh
3. **Follow-up** trong cùng phiên để đào sâu
4. **Luôn kiểm chứng** nguồn trích dẫn — AI không phải trọng tài chân lý
5. **Theo dõi "Show thinking"** để phát hiện nguồn ẩn giá trị

---

*Nguồn: Meta-research từ `docs/01_prompting/deepsearch/2026-03-20_meta-research-ket-qua.md`*
