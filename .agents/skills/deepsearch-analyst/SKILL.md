---
name: deepsearch-analyst
description: Phân tích và cấu trúc hóa kết quả nghiên cứu từ Google DeepSearch thành tài liệu có hệ thống
---

# Goal

Xử lý kết quả thô từ Google DeepSearch thành tài liệu cấu trúc hóa, rút trích kiến thức cốt lõi, và cập nhật các file liên quan trong dự án.

# Instructions

1. **Đọc kết quả thô** từ user (paste từ DeepSearch)
2. **Xác định folder lưu trữ** phù hợp trong `docs/`
3. **Cấu trúc hóa** thành file `YYYY-MM-DD_[ten]-ket-qua.md`:
   - Tóm tắt điều hành (5-10 dòng)
   - Chia thành các phần rõ ràng với heading
   - Tạo bảng so sánh khi có nhiều thông tin đối chiếu
   - Đánh dấu insight mới bằng 💡
   - Ghi rõ metadata: ngày, nguồn, prompt đã dùng
4. **Rút trích** kiến thức áp dụng được → cập nhật file liên quan:
   - `PROMPT_GUIDE.md` nếu có kỹ thuật viết prompt mới
   - `WORKFLOW.md` nếu có quy trình mới
   - `ANTIGRAVITY_GUIDE.md` nếu về công cụ
5. **Chuyển brief** từ `dang-lam/` → `hoan-thanh/`
6. **Ghi CHANGELOG**

# Examples

**Input**: User paste bài nghiên cứu dài 3000 từ về "Kỹ thuật viết prompt cho DeepSearch"

**Output**:
- File: `docs/01_prompting/deepsearch/2026-03-20_meta-research-ket-qua.md`
  - Tóm tắt: 7 phần cốt lõi
  - Bảng: sai lầm phổ biến + cách khắc phục
  - Insight: Khung 4 Phần, Criteria-First, phân rã đa phiên
- Cập nhật: `PROMPT_GUIDE.md` với template mới
- Changelog entry mới

# Constraints

- KHÔNG tự ý bỏ qua thông tin từ kết quả nghiên cứu — cấu trúc hóa TẤT CẢ
- KHÔNG thêm thông tin không có trong nguồn (tránh hallucination)
- Mỗi file kết quả PHẢI có metadata header (ngày, nguồn, prompt)
- Luôn tạo bảng tóm tắt cho dữ liệu so sánh
- Ghi rõ "⚠️ Chưa xác minh" cho thông tin cần kiểm chứng thêm
