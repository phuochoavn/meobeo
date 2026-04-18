# 🚫 Sai lầm & Bài học rút ra

Ghi nhận các sai lầm trong quá trình phát triển dự án để tránh lặp lại.

## Format ghi chép

```
### [Ngày] — [Tiêu đề ngắn]
- **Sai lầm**: Mô tả sai lầm
- **Nguyên nhân**: Tại sao xảy ra
- **Hậu quả**: Ảnh hưởng như thế nào
- **Bài học**: Rút ra được gì
- **Cách tránh**: Làm gì để không lặp lại
```

---

### 2026-03-20 — Lưu prompt sai chỗ
- **Sai lầm**: Lưu file prompt (brief) trong `docs/01_prompting/deepsearch/` thay vì `project/briefs/`
- **Nguyên nhân**: Lẫn lộn giữa "kết quả nghiên cứu" (thuộc docs/) và "brief công việc" (thuộc project/briefs/)
- **Hậu quả**: Khó theo dõi trạng thái brief đang làm / đã xong
- **Bài học**: Prompt = brief công việc → luôn lưu trong `project/briefs/`. Kết quả = tài liệu → lưu trong `docs/`
- **Cách tránh**: Đã thêm "Brief Routing" vào GEMINI.md để agent nhớ quy tắc

*Chưa có entry nào khác — đây là điều tốt! 🎉*
