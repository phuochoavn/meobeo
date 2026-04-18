# 🤖 Hướng Dẫn Vận Hành Antigravity — Dự án Mèo Ú Nấu Ăn

> Cập nhật: 2026-03-20 (bổ sung benchmark data từ DeepSearch)
> Models: Google Ultra (Gemini 3.1 Pro) + Claude Opus 4.6

---

## 1. Antigravity Là Gì?

Antigravity là **Agentic AI IDE** — một môi trường phát triển dùng AI agent tự trị để:
- Đọc/viết/chỉnh sửa file
- Chạy lệnh terminal
- Duyệt web & nghiên cứu
- Quản lý dự án qua artifacts (task.md, implementation_plan.md, walkthrough.md)
- Lưu trí nhớ dài hạn qua **Knowledge Items (KI)**

---

## 2. Hệ Thống Model — Cách Chọn Model Cho Từng Task

### Bạn đang có:
| Model | Ký hiệu | Mạnh nhất ở |
|-------|----------|-------------|
| **Claude Opus 4.6** | 🧠 Opus | Kiến trúc, phân tích sâu, lập plan, code phức tạp |
| **Google Ultra / Gemini 3.1 Pro** | ⚡ Ultra | Suy luận chuyên sâu, tiếng Việt tự nhiên, context 1M token |

### Benchmark so sánh (Q1/2026):

| Benchmark | Gemini 3.1 Pro (Ultra) | Claude Opus 4.6 | Thắng |
|-----------|----------------------|-----------------|-------|
| ARC-AGI-2 (suy luận) | **77.1%** | 68.8% | ⚡ Ultra |
| GPQA Diamond (cấp TS) | **94.3%** | 91.3% | ⚡ Ultra |
| Terminal-Bench 2.0 (coding) | — | **65.4%** | 🧠 Opus |
| MCP Atlas (tool-calling) | **69.2%** | 59.5% | ⚡ Ultra |
| MMMLU (đa ngôn ngữ/Việt) | **92.6%** | 91.1% | ⚡ Ultra |
| Tốc độ | **109.5 t/s** | ~71 t/s | ⚡ Ultra |
| Chi phí (1M token) | **$2.00** | $15.00 | ⚡ Ultra (7.5x rẻ) |
| Hallucination rate | Cao hơn | **0.8%** | 🧠 Opus |

### Quy tắc chọn model cho dự án:

| Task cụ thể | Model nên dùng | Lý do |
|-------------|----------------|-------|
| **Lập kế hoạch, viết brief** | 🧠 Opus 4.6 | Hallucination 0.8%, chi tiết |
| **Tiếng Việt, prompt writing** | ⚡ Ultra | MMMLU 92.6%, tự nhiên nhất |
| **Tool-calling, automation** | ⚡ Ultra | MCP Atlas 69.2% |
| **Backend audit, tài liệu dài** | 🧠 Opus 4.6 | Verbosity cao, edge cases |
| **Kiểm thử tự động** | ⚡ Ultra | 7.5x rẻ hơn, nhanh |
| **Viết prompt Gemini Video** | ⚡ Ultra | Hiểu ecosystem Google |
| **QA, review chất lượng** | 🧠 Opus 4.6 | Elo 1606 expert tasks |

### Cách chuyển model:
- Trong Antigravity: nhấn dropdown model ở thanh chat
- Model mới chỉ có hiệu lực từ **tin nhắn tiếp theo**

---

## 3. Hệ Thống Agents & Skills

### Agents là gì?
Agent = AI tự trị với **vai trò cụ thể** + **quy tắc** + **tools** (terminal, file, browser).

- **Mission Control**: Điều phối nhiều agent song song (ví dụ: 5 agent sửa 5 bug cùng lúc)
- **Editor View**: Soạn thảo VS Code với inline commands
- **Browser Subagent**: Mô phỏng thao tác web để kiểm tra UI

### Skills là gì?
Skills = **gói tri thức mô-đun hóa** — ở trạng thái "ngủ" cho đến khi cần.

**Triết lý Progressive Disclosure**: Không tải tất cả → chỉ kích hoạt khi relevant.

**Hai cấp lưu trữ:**
| Cấp | Đường dẫn | Phạm vi |
|-----|-----------|--------|
| Workspace | `<project>/.agents/skills/<skill>/` | Riêng dự án |
| Global | `~/.gemini/antigravity/skills/<skill>/` | Tất cả dự án |

**Cấu trúc SKILL.md chuẩn:**
```markdown
# Goal
Kết quả kỳ vọng cụ thể

# Instructions
Phương pháp luận (hướng dẫn AI cách lập luận)

# Examples
Cặp input/output mẫu (few-shot)

# Constraints
- CRITICAL: Quy tắc phủ định (KHÔNG được xóa DB, KHÔNG viết vào cache...)
```

### Workflows là gì?
Workflows = **quy trình tự động hóa** gọi bằng `/workflow-name`.
- Lưu trong `.agents/workflows/`
- `// turbo`: Auto-run 1 bước
- `// turbo-all`: Auto-run MỌI bước → agent chạy hoàn toàn tự động

---

## 4. Artifacts — Hệ Thống Quản Lý Task

Antigravity tự động tạo & quản lý:

| Artifact | Mục đích | Khi nào tạo |
|----------|----------|-------------|
| `task.md` | Checklist tracking tiến độ | Đầu mỗi task phức tạp |
| `implementation_plan.md` | Kế hoạch kỹ thuật chi tiết | Khi cần review trước khi làm |
| `walkthrough.md` | Tổng kết kết quả | Sau khi hoàn thành |

---

## 5. Knowledge Items (KI) — Trí Nhớ Dài Hạn

- AI **tự động** tóm tắt cuộc hội thoại thành KI sau mỗi phiên
- KI lưu trong `~/.gemini/antigravity/knowledge/`
- Phiên mới: AI tự đọc KI summaries để nhớ ngữ cảnh cũ

**Quan trọng cho dự án Mèo Ú**:
- Mọi nghiên cứu DeepSearch đã xử lý sẽ được AI ghi nhớ qua KI, không cần paste lại
- **Nhân vật Mèo Ú**: Nguồn sự thật DUY NHẤT là `project/nhan-vat/MEO_U_CHARACTER_BIBLE.md` — Mèo Ú là mèo **SIÊU MẬP**, mèo trần tự nhiên (không mũ/khăn), style semi-realistic, bối cảnh đồng quê VN. PHẢI đọc Bible trước khi viết prompt video/ảnh.

---

## 6. Cấu Hình Tối Ưu Cho Windows

### GEMINI.md (Global Rules)
File `GEMINI.md` ở root dự án chứa quy tắc bắt buộc cho agent:

```markdown
# Quy tắc dự án Mèo Ú Nấu Ăn

## Môi trường
- OS: Windows 11
- Shell: PowerShell + cmd /c wrapper
- Ngôn ngữ: Tiếng Việt

## Terminal Rules
- LUÔN dùng `cmd /c` trước mọi lệnh terminal
- KHÔNG dùng `cd` — dùng parameter `Cwd` thay thế

## Quy trình làm việc
- Mọi task lớn → tạo brief trong `project/briefs/dang-lam/`
- Sau khi xong → chuyển brief sang `project/briefs/hoan-thanh/`
- Ghi changelog vào `project/lich-su/CHANGELOG.md`
- Sai lầm → ghi vào `project/lich-su/SAI_LAM_VA_BAI_HOC.md`

## Đặt tên file
- Tài liệu nghiên cứu: `YYYY-MM-DD_ten-chu-de.md`
- Brief: `YYYY-MM-DD_ten-task.md`
```

### Settings khuyến nghị
```json
{
    "antigravity.terminal.commandAutoExecution": "turbo",
    "antigravity.agent.reviewPolicy": "alwaysProceed"
}
```

---

## 7. Tips Sử Dụng Hiệu Quả

### ✅ Nên làm
1. **Một task rõ ràng mỗi lần** — tránh yêu cầu 10 thứ cùng lúc
2. **Review plan trước khi approve** — đọc kỹ implementation_plan.md
3. **Dùng đúng model** — Opus cho logic, Ultra cho tiếng Việt & research
4. **Tận dụng follow-up** — AI nhớ ngữ cảnh trong cùng phiên
5. **Ghi feedback cụ thể** — "sai ở dòng X, sửa thành Y" tốt hơn "sai rồi"

### ❌ Không nên
1. **Không nhập quá nhiều task vào 1 message** — AI dễ quên/lỗi
2. **Không bỏ qua plan review** — đây là điểm kiểm soát quan trọng nhất
3. **Không quên cmd /c** trên Windows — sẽ khiến terminal treo
4. **Không dùng `cd`** — luôn dùng Cwd parameter
