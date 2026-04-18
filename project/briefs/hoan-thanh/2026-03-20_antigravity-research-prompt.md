# Nghiên cứu: Antigravity Agentic IDE — Agents, Skills & Workflows

> **Ngày**: 2026-03-20
> **Nguồn**: Google DeepSearch
> **Folder lưu kết quả**: `docs/01_prompting/deepsearch/`
> **Trạng thái**: ✅ Đã gửi & nhận kết quả → `2026-03-20_antigravity-research-ket-qua.md`

---

## Prompt gửi cho Google DeepSearch

```
Đóng vai một chuyên gia về AI Agentic IDE và tự động hóa quy trình phát triển phần mềm.

Nhiệm vụ: Phân tích toàn diện về Antigravity IDE (Windsurf) — một môi trường phát triển tích hợp AI agent tự trị, được xây dựng trên nền tảng VS Code, sử dụng các mô hình ngôn ngữ lớn như Claude Opus 4.6 và Google Gemini 3.1 Pro (Ultra).

Nghiên cứu chuyên sâu các khía cạnh sau:

1. **Kiến trúc Agent trong Antigravity**: Cách hệ thống agent hoạt động — bao gồm cơ chế planning (lập kế hoạch), execution (thực thi), và verification (kiểm chứng). Phân tích flow xử lý: từ khi nhận prompt người dùng → phân tích task → gọi tools (terminal, file edit, browser) → trả kết quả.

2. **Hệ thống Skills**: Cách thiết kế và tổ chức các "skill" (kỹ năng chuyên biệt) cho agent. Cấu trúc folder `.agents/skills/`, file `SKILL.md`, và cách agent đọc & thực thi skills. Best practices cho việc tạo custom skills.

3. **Workflows & Automation**: Cách xây dựng workflows tự động trong `.agents/workflows/`. Cú pháp `// turbo` và `// turbo-all` để bypass xác nhận thủ công. Chiến lược thiết kế workflow cho các tác vụ lặp lại.

4. **Model Routing Strategy**: So sánh chi tiết Claude Opus 4.6 vs Google Gemini 3.1 Pro (Ultra) trong bối cảnh Agentic IDE — bao gồm: reasoning ability, context window, hallucination rate, tool-calling reliability, tiếng Việt proficiency, và tốc độ xử lý. Khi nào nên dùng model nào?

5. **Knowledge Items (KI) & Cross-conversation Memory**: Cách hệ thống trí nhớ dài hạn hoạt động — từ việc tự động sinh KI sau mỗi phiên, đến cách agent sử dụng KI để duy trì ngữ cảnh xuyên suốt các cuộc hội thoại.

6. **Artifacts System**: Cách quản lý các artifact chuẩn (task.md, implementation_plan.md, walkthrough.md) — quy trình PLANNING → EXECUTION → VERIFICATION.

7. **Tối ưu hóa trên Windows**: Các vấn đề phổ biến khi chạy Antigravity trên Windows (EOF signal failure, terminal hang, Language Server memory leak) và cách giải quyết.

8. **So sánh với các Agentic IDE khác**: Antigravity vs Cursor vs GitHub Copilot Workspace vs Devin vs Windsurf (Codeium) — điểm mạnh, điểm yếu, và use case phù hợp.

Ràng buộc:
- Ưu tiên thông tin từ tài liệu chính thức, blog kỹ thuật có uy tín, và kinh nghiệm thực tế từ cộng đồng developer
- Bỏ qua các bài viết marketing chung chung không có chi tiết kỹ thuật
- Nếu không tìm thấy thông tin cho mục nào, ghi rõ "Dữ liệu không khả dụng" thay vì ước tính
- Phân biệt rõ giữa tính năng đã xác nhận và tính năng đang phát triển

Trình bày kết quả dưới dạng báo cáo có cấu trúc Markdown, sử dụng bảng so sánh cho các thông số kỹ thuật, và trích dẫn nguồn cho mỗi phát hiện quan trọng.
```

---

## Kỳ vọng thu hoạch

- Kiến thức mới về agent architecture mà KI hiện tại chưa có
- So sánh model mới nhất (Opus 4.6 vs Ultra) — cập nhật benchmark 2026
- Kỹ thuật tạo custom skills & workflows chưa biết
- So sánh với đối thủ (Cursor, Copilot Workspace) để biết advantage
- Tips tối ưu Windows mới
