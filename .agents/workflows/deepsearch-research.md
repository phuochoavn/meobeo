---
description: Quy trình nghiên cứu DeepSearch từ viết prompt đến lưu kết quả
---

# Quy trình Nghiên cứu DeepSearch

// turbo-all

## Bước thực hiện

1. Xác định chủ đề nghiên cứu và folder lưu trữ trong `docs/`

2. Viết prompt theo **Khung 4 Phần** (xem `project/tro-ly/PROMPT_GUIDE.md`):
   - Vai trò (Persona)
   - Nhiệm vụ (Task) — dùng động từ mạnh
   - Ràng buộc (Constraints) — cấm nguồn kém, cấm ước tính
   - Đầu ra (Output Format)

3. Lưu prompt vào file `docs/[folder]/YYYY-MM-DD_[ten-chu-de]-prompt.md`

4. Gửi prompt cho Google DeepSearch
   - **QUAN TRỌNG**: Review Edit Plan trước khi nhấn Start Research
   - Theo dõi "Show thinking" để phát hiện nguồn ẩn

5. Nhận kết quả → paste cho Antigravity để xử lý:
   - Cấu trúc hóa thành các phần rõ ràng
   - Tạo bảng tóm tắt
   - Lưu vào `docs/[folder]/YYYY-MM-DD_[ten-chu-de]-ket-qua.md`

6. Rút trích kiến thức → cập nhật các file liên quan:
   - `project/tro-ly/PROMPT_GUIDE.md` (nếu có kỹ thuật mới)
   - `project/tro-ly/WORKFLOW.md` (nếu có quy trình mới)
   - `project/lich-su/CHANGELOG.md`

7. Cập nhật trạng thái file prompt: `⏳ Chờ gửi` → `✅ Hoàn thành`
