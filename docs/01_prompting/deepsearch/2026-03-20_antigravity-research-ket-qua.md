# Nghiên Cứu Chuyên Sâu: Kiến Trúc Antigravity IDE

> **Ngày**: 2026-03-20
> **Nguồn**: Google DeepSearch
> **Prompt**: Xem `2026-03-20_antigravity-research-prompt.md`
> **Trạng thái**: ✅ Hoàn thành

---

## Tóm Tắt Điều Hành

Nghiên cứu 8 chiều kích của Antigravity IDE: kiến trúc agent đa luồng, hệ thống Skills (Progressive Disclosure), Workflows (`// turbo`), model routing (Opus 4.6 vs Gemini 3.1 Pro), Knowledge Items, Artifacts, Windows issues, và so sánh competitors.

---

## 1. Kiến Trúc Agent — Hệ Thống Đa Tác Nhân

### Hai không gian chức năng:
| Không gian | Vai trò |
|-----------|---------|
| **Mission Control** | Trung tâm chỉ huy — khởi tạo, giám sát nhiều agent song song |
| **Editor View** | Soạn thảo VS Code — chỉnh sửa nội tuyến, inline commands |

### Luồng xử lý 3 giai đoạn:
1. **Tiếp nhận & Cấu hình**: Planning mode (task lớn) vs Fast mode (task vi mô)
2. **Tool-calling**: Terminal, JavaScript, Browser Subagent (mô phỏng thao tác web)
3. **Kiểm chứng**: Screenshots, Browser Recordings, Feedback loop ("Google Docs-style comments")

### 💡 Insight mới:
- **Parallel agents**: Có thể chạy 5 agent cùng lúc xử lý 5 bug khác nhau
- **Browser Subagent**: Tự kiểm tra UI bằng cách mô phỏng người dùng thật
- **Feedback loop**: Bôi đen code → comment → agent tự sửa

---

## 2. Hệ Thống Skills — Triết Lý "Tiết Lộ Lũy Tiến"

### Nguyên lý Progressive Disclosure:
- Skills ở trạng thái **ngủ** (dormant) → không tốn context window
- Chỉ **kích hoạt** khi task có relevance matching cao

### Hai cấp độ lưu trữ:

| Cấp | Đường dẫn | Phạm vi |
|-----|-----------|---------|
| **Workspace** | `<project>/.agents/skills/<skill>/` | Riêng cho dự án |
| **Global** | `~/.gemini/antigravity/skills/<skill>/` | Tất cả dự án |

### Quy trình 3 bước:
1. **Discovery**: Quét tiêu đề + description của tất cả skills
2. **Activation**: Nạp SKILL.md khi relevance matching cao
3. **Execution**: Tuân thủ chỉ thị trong skill

### Cấu trúc SKILL.md tối ưu (4 thành phần):

| Thành phần | Vai trò | Ví dụ |
|-----------|---------|-------|
| **Goal** | Kết quả kỳ vọng | "Phân tích cấu trúc lược đồ dữ liệu" |
| **Instructions** | Phương pháp luận (không phải lệnh cứng) | Hướng dẫn AI cách lập luận |
| **Examples** | Few-shot input/output | Định chuẩn format đầu ra |
| **Constraints** | Quy tắc phủ định (CRITICAL) | "KHÔNG xóa DB", "KHÔNG viết file vào cache" |

---

## 3. Workflows & Automation

### Cấu trúc workflow:
```yaml
---
description: [mô tả ngắn]
---
## Objective
[mục tiêu]
## Process
[các bước]
```

### Cú pháp turbo:

| Cú pháp | Phạm vi | Hành vi |
|---------|---------|---------|
| `// turbo` | 1 bước duy nhất | SafeToAutoRun=true cho lệnh ngay sau |
| `// turbo-all` | Toàn bộ workflow | Mọi run_command đều auto-run |

### 💡 Insight: `// turbo-all` biến agent thành **cộng sự kỹ thuật số** tự động — đọc config, setup, test, report mà không cần giám sát.

---

## 4. Model Routing — Opus 4.6 vs Gemini 3.1 Pro (Ultra)

### Benchmark so sánh (2026):

| Tiêu chí | Gemini 3.1 Pro | Claude Opus 4.6 | Thắng |
|----------|---------------|-----------------|-------|
| **ARC-AGI-2** (suy luận trừu tượng) | **77.1%** | 68.8% | ⚡ Gemini |
| **GPQA Diamond** (cấp Tiến sĩ) | **94.3%** | 91.3% | ⚡ Gemini |
| **Terminal-Bench 2.0** (coding E2E) | — | **65.4%** | 🧠 Opus |
| **MCP Atlas** (tool-calling đa bước) | **69.2%** | 59.5% | ⚡ Gemini |
| **GDPval-AA** (phân tích cấp chuyên gia) | Elo 1317 | **Elo 1606** | 🧠 Opus |
| **MMMLU** (đa ngôn ngữ/Việt) | **92.6%** | 91.1% | ⚡ Gemini |
| **Tốc độ** | **109.5 t/s** | ~71 t/s | ⚡ Gemini |
| **Chi phí (1M token input)** | **$2.00** | $15.00 | ⚡ Gemini (7.5x rẻ hơn) |
| **Hallucination** | Cao hơn | **Thấp (0.8%)** | 🧠 Opus |
| **Verbosity/chi tiết tài liệu** | Tóm tắt quá mức | **Chi tiết, edge cases** | 🧠 Opus |

### Chiến lược routing tối ưu:

| Task | Model | Lý do |
|------|-------|-------|
| Kiến trúc vĩ mô, planning | 🧠 Opus | Zero-hallucination, chi tiết |
| Tool-calling đa bước, CI/CD | ⚡ Gemini | 69.2% MCP Atlas, nhanh |
| Tiếng Việt | ⚡ Gemini | MMMLU 92.6% |
| Backend audit, tài liệu dài | 🧠 Opus | Elo 1606, verbosity cao |
| Kiểm thử tự động tần suất cao | ⚡ Gemini | 7.5x rẻ hơn |

---

## 5. Knowledge Items (KI) — Trí Nhớ Dài Hạn

### Cơ chế:
- **Tự động**: Background subagent phân tích & chắt lọc patterns thành KI
- **Lưu trữ**: `~/.gemini/antigravity/knowledge/` + `.pb` files
- **Khởi phiên**: Agent rà soát KI summaries → tải nếu relevant

### ⚠️ Vấn đề trên Windows:
- KI **không tự sinh** trên Windows 11 (fail silently)
- Thư mục `knowledge/` trống — chỉ có `knowledge.lock`
- 24/30 conversations không có logs
- **Nguyên nhân**: Background subagents xung đột với quá trình Windows
- **Workaround hiện tại**: Chưa có giải pháp hoàn chỉnh — phụ thuộc bản vá từ Google

> **Lưu ý cho dự án**: Dù KI có vấn đề tự sinh trên Windows, chúng ta vẫn dùng KI được vì Antigravity vẫn đọc được KI đã tồn tại. Quan trọng là duy trì tài liệu trong `project/` như safety net.

---

## 6. Artifacts System

### 3 tạo tác chuẩn + vai trò:

| Artifact | Giai đoạn | Chức năng |
|----------|----------|-----------|
| `task.md` | PLANNING | Living checklist — phân rã task thành action items |
| `implementation_plan.md` | PLANNING | Thiết kế kỹ thuật — phải được approve trước EXECUTION |
| `walkthrough.md` | VERIFICATION | Tổng kết + screenshots + browser recordings |

### Công cụ `task_boundary`: chuyển trạng thái PLANNING → EXECUTION → VERIFICATION

---

## 7. Tối Ưu Windows

| Vấn đề | Triệu chứng | Giải pháp |
|--------|-------------|-----------|
| **EOF failure** | Terminal treo "Running..." | `cmd /c` trong GEMINI.md |
| **Memory leak** | RAM 1.3GB → 13GB trong 15 phút | Modularize code, chờ bản vá |
| **AI memory drift** | Agent quên `cmd /c` khi phiên dài | Nudge: "Follow global rules" |
| **Workspace Trust** | Không Trust = IDE bị vô hiệu hóa | Phải Trust workspace |

### LSP Mitigation Stack:
- Tạo `.antigravityignore` chặn `node_modules/`
- Xóa cache: `%APPDATA%\Antigravity\Cache\*`
- Chia file code lớn thành modules nhỏ

---

## 8. So Sánh Competitors (LMArena Q1/2026)

| Tiêu chí | Antigravity | Cursor | Windsurf | Copilot |
|----------|------------|--------|----------|---------|
| **Tự trị (Autonomy)** | **95/100** | Thấp | 88/100 | Thấp |
| **Dễ dùng (Ease of Use)** | 82/100 | Cao | **96/100** | Cao |
| **Linh hoạt (Flexibility)** | **94/100** | Trung bình | 86/100 | Thấp |
| **SWE-bench** | **76.2%** | **~77%** | — | — |
| **Multi-agent** | ✅ (5 agent song song) | ❌ | ❌ | ❌ |
| **Artifacts/lưu vết** | ✅ Toàn diện | ❌ | ❌ | ❌ |
| **RAG indexing** | Cơ bản | Tốt | **Xuất sắc** | Tốt |
| **Windows stability** | ⚠️ Preview | ✅ | ✅ | ✅ |

### Ai nên dùng gì:
- **Cursor**: Dev solo, muốn control từng dòng code
- **Windsurf**: Team lớn, enterprise monorepo
- **Antigravity**: Architect, PM, multi-service projects
- **Copilot**: Khám phá AI nhẹ nhàng, không đổi tool
