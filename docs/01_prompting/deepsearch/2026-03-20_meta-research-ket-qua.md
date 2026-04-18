# Báo Cáo Nghiên Cứu: Nghệ Thuật Thiết Kế Câu Lệnh Cho Google Gemini Deep Research

> **Ngày nghiên cứu**: 2026-03-20
> **Nguồn**: Google DeepSearch (meta-research)
> **Prompt đã dùng**: Xem file `2026-03-20_meta-research-prompt.md`
> **Trạng thái**: ✅ Hoàn thành

---

## Tóm Tắt Điều Hành

Nghiên cứu này phân tích toàn diện phương pháp viết prompt tối ưu cho Google Gemini Deep Research — một hệ thống AI tác nhân tự trị (Agentic AI) hoạt động như "nhà phân tích độc lập", thực hiện chu trình: lập kế hoạch → duyệt web → phân tích chéo → tổng hợp báo cáo có trích dẫn.

---

## 1. Khung Cấu Trúc 4 Phần (4-Part Framework)

### 1.1 Vai trò (Persona)
- Chỉ định vai trò chuyên gia cụ thể để giới hạn không gian xác suất
- **Tốt**: "Đóng vai một Giám đốc Chiến lược GTM"
- **Kém**: Không chỉ định vai trò → câu trả lời chung chung kiểu bách khoa

### 1.2 Nhiệm vụ Cốt lõi (Task)
- Dùng **động từ hành động mạnh**: "Phân tích", "Tổng hợp", "So sánh đối chiếu", "Xây dựng mô hình"
- **Tránh**: "Hãy nói cho tôi biết về...", "Khám phá chủ đề..." → chỉ thu thập bề mặt

### 1.3 Ngữ cảnh & Ràng buộc (Context & Constraints)
- Giải thích **tại sao** nghiên cứu cần thiết
- Xác định **đối tượng đọc**
- **Ràng buộc tiêu cực** (cực kỳ quan trọng):
  - "Chỉ trích xuất từ báo cáo đã kiểm toán"
  - "Bỏ qua blog cá nhân và diễn đàn"
  - "Dùng 'Dữ liệu không khả dụng' thay vì ước tính"

### 1.4 Định dạng Đầu ra (Output Format)
- Quy định cấu trúc cụ thể: tóm tắt điều hành (max 200 từ), bảng ma trận, Markdown, JSON...
- AI sắp xếp tốt hơn khi biết trước hình hài kết quả

---

## 2. Kỹ Thuật Phân Định XML & Quy Tắc Ngữ Cảnh Dài

### Thẻ XML phân định
- Dùng thẻ `<instructions>`, `<constraints>`, `<context>`, `<output_format>` để tạo ranh giới rõ ràng
- Ngăn ngừa **trôi dạt chỉ thị** (instruction drift) và **tiêm nhiễm prompt** (prompt injection)

### Quy tắc sắp xếp
- **Đầu prompt**: Vai trò, hướng dẫn, ràng buộc
- **Cuối prompt**: Dữ liệu thô (sách, báo cáo, mã nguồn)
- **Mẹo**: Lặp lại chỉ thị ngắn ở cuối cùng: "Dựa trên các thông tin ở trên, hãy..."

---

## 3. Kỹ Thuật Đặt Câu Hỏi

### Câu hỏi mở rộng → Giai đoạn khám phá
- Quét radar tầm xa, bản đồ hóa không gian kiến thức
- Nhược điểm: thiếu tính ứng dụng sắc bén

### Câu hỏi cụ thể → Giai đoạn phân tích sâu
- **Chiến lược "Ưu tiên Tiêu chí"**: Yêu cầu AI tự định danh 5 thông số quan trọng nhất → rồi so sánh dựa trên đúng 5 thông số đó
- Triệt tiêu danh sách ưu/nhược điểm chung chung

### Phân rã tuyến tính đa phiên
- **KHÔNG** nhồi 100 trang vào 1 prompt
- Chia thành các phân hệ độc lập → mỗi phiên DeepSearch riêng biệt
- Phiên cuối cùng: tổng hợp, AI đóng vai tổng biên tập

---

## 4. Sai Lầm Phổ Biến & Cách Khắc Phục

| Sai lầm | Nguyên nhân | Giải pháp |
|---------|-------------|-----------|
| **Quá tải ngữ cảnh** | Nạp >10 file cùng lúc | Chuyển PDF→Markdown, nạp dần từng nhóm |
| **Ảo giác lập luận** | AI bịa dữ liệu khi không tìm thấy | Cho phép AI "thất bại": "Ghi 'Dữ liệu không khả dụng'" |
| **Đứt gãy trích dẫn** | Mất nguồn gốc qua nhiều vòng nghiên cứu | Yêu cầu bảo tồn URL/tên bài báo gốc |
| **Trôi dạt chỉ thị** | Prompt quá dài, AI quên quy tắc | Dùng thẻ XML + ghi "tuân thủ định dạng là ưu tiên số 1" |
| **Đơn giản hóa quá mức** | Phiên kéo dài, AI "lười" | Dùng Keyword Triggers, nhấn mạnh ưu tiên |

---

## 5. Kỹ Thuật Nâng Cao

### 5.1 Khung Mô Phỏng Tranh Luận (Debate Simulator)
- 2 chuyên gia đối nghịch tranh luận → 1 trọng tài tổng kết
- Triệt tiêu thiên kiến một chiều

### 5.2 Khung Góc Nhìn Đa Tầng (Layered Perspective)
- Giải thích theo 3 cấp: Beginner → Practitioner → Expert
- Mỗi cấp có 1 ví dụ thực tiễn

### 5.3 Khung Cỗ Máy Thời Gian (Time Machine)
- Phân tích: 10 năm trước → hiện tại → 10 năm tới
- Nhấn mạnh 3 sự dịch chuyển cấu trúc quan trọng

### 5.4 Hội Đồng Phân Tích (Analyst Panel)
- Chạy 3-5 báo cáo với persona khác nhau
- Tổng hợp: tìm mâu thuẫn, chủ đề xuyên suốt

### 5.5 Cưỡng Chế Nguồn Dữ Liệu
- Tắt Google Search mặc định nếu cần
- Chỉ định nguồn: .edu, .gov, Gartner, McKinsey
- **Mẹo đọc AI**: Nhiều trích dẫn (8-12) = AI ít tự tin → cần kiểm chứng kỹ

---

## 6. Best Practices Từ Cộng Đồng

1. **Xác tín độc lập**: Luôn check lại nguồn trích dẫn — AI không phải trọng tài chân lý
2. **Theo dõi "Show thinking"**: Quan sát luồng suy diễn real-time để tìm nguồn ẩn
3. **Follow-up Refinement**: Báo cáo đầu tiên chỉ là khung xương → tiếp tục đào sâu trong cùng phiên
4. **Edit Plan**: Điểm can thiệp quyền lực nhất — review kế hoạch trước khi AI chạy

---

## 7. Chiến Lược Agentic RAG vs Prompt Chaining

| Phương pháp | Khi nào dùng |
|-------------|-------------|
| **Prompt Stuffing** | Dữ liệu đã có sẵn, JSON/báo cáo dài |
| **Phân rã đa phiên** | Chủ đề quá rộng, >20 tiểu mục |
| **Agentic RAG** (Deep Research) | Nghiên cứu khám phá, dữ liệu cần truy xuất từ web |
| **Prompt Chaining cũ** | ❌ Lỗi thời — cửa sổ ngữ cảnh triệu token đã thay thế |
