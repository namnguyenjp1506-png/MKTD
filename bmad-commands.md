# BMAD — Danh sách Slash Commands

> Tài liệu tham khảo nhanh toàn bộ lệnh BMAD có trong dự án.
> Gọi bằng cách nhập `/tên-lệnh` trong Claude Code.
> Mỗi workflow nên chạy trong **context window mới**.

---

## PHASE 1 — Phân tích (Analysis)

> Không bắt buộc, nhưng nên làm để có nền tảng tốt cho PRD.

| Lệnh | Tên | Agent | Mục đích |
|---|---|---|---|
| `/bmad-brainstorming` | Brainstorm dự án | 📊 Mary (Analyst) | Khám phá ý tưởng qua các kỹ thuật brainstorm đa dạng. Dùng khi mới bắt đầu hoặc khi cần ý tưởng mới |
| `/bmad-market-research` | Nghiên cứu thị trường | 📊 Mary | Phân tích cạnh tranh, nhu cầu khách hàng, xu hướng thị trường |
| `/bmad-domain-research` | Nghiên cứu domain | 📊 Mary | Tìm hiểu sâu về ngành/lĩnh vực: thuật ngữ chuyên ngành, đặc thù vận hành |
| `/bmad-technical-research` | Nghiên cứu kỹ thuật | 📊 Mary | Đánh giá tính khả thi kỹ thuật, lựa chọn kiến trúc và hướng triển khai |
| `/bmad-create-product-brief` | Tạo Product Brief | 📊 Mary | Đóng khung ý tưởng sản phẩm — bước đầu tiên để định hình dự án |

---

## PHASE 2 — Lập kế hoạch (Planning)

> ⚠️ **Tạo PRD là bắt buộc** trước khi sang Phase 3.

| Lệnh | Tên | Agent | Bắt buộc | Mục đích |
|---|---|---|---|---|
| `/bmad-create-prd` | Tạo PRD | 📋 John (PM) | ✅ **BẮT BUỘC** | Tạo tài liệu yêu cầu sản phẩm (Product Requirements Document) — nền tảng của toàn bộ dự án |
| `/bmad-validate-prd` | Kiểm tra PRD | 📋 John | Không | Xác nhận PRD đầy đủ, rõ ràng, nhất quán trước khi tiếp tục |
| `/bmad-edit-prd` | Chỉnh sửa PRD | 📋 John | Không | Cập nhật và cải thiện PRD đã có |
| `/bmad-create-ux-design` | Thiết kế UX | 🎨 Sally (UX) | Không | Lập kế hoạch UX/UI — nên làm nếu sản phẩm có giao diện người dùng |

---

## PHASE 3 — Giải pháp kỹ thuật (Solutioning)

> ⚠️ Cả 3 bước đều bắt buộc trước khi triển khai.

| Lệnh | Tên | Agent | Mục đích |
|---|---|---|---|
| `/bmad-create-architecture` | Thiết kế kiến trúc | 🏗️ Winston (Architect) | Ghi lại các quyết định kỹ thuật, sơ đồ hệ thống, thiết kế tổng thể |
| `/bmad-create-epics-and-stories` | Tạo Epics & Stories | 📋 John (PM) | Phân rã yêu cầu thành các Epic (nhóm lớn) và User Story (tính năng cụ thể) |
| `/bmad-check-implementation-readiness` | Kiểm tra sẵn sàng | 🏗️ Winston | Đảm bảo PRD, UX, Architecture và Stories đồng bộ — cửa ngõ vào triển khai |

---

## PHASE 4 — Triển khai (Implementation)

> Vòng lặp: SP → CS → VS → DS → CR → CS tiếp theo...

| Lệnh | Tên | Agent | Bắt buộc | Mục đích |
|---|---|---|---|---|
| `/bmad-sprint-planning` | Lập kế hoạch Sprint | 🏃 Bob (SM) | ✅ **BẮT BUỘC** | Tạo kế hoạch sprint — khởi động phase triển khai |
| `/bmad-sprint-status` | Trạng thái Sprint | 🏃 Bob | Không | Xem tiến độ sprint hiện tại, phát hiện rủi ro |
| `/bmad-create-story` | Chuẩn bị Story | 🏃 Bob | ✅ | Chuẩn bị story tiếp theo trong sprint plan đưa vào dev |
| `/bmad-dev-story` | Dev Story | 💻 Amelia (Dev) | ✅ | Thực thi triển khai story theo spec đã chuẩn bị |
| `/bmad-qa-generate-e2e-tests` | Tạo test tự động | 🧪 Quinn (QA) | Không | Sinh test API và E2E tự động cho code đã triển khai |
| `/bmad-code-review` | Review code | 💻 Amelia | Không | Review code theo nhiều lớp: blind hunt, edge case, acceptance |
| `/bmad-retrospective` | Tổng kết Epic | 🏃 Bob | Không | Review cuối epic — rút bài học, đánh giá kết quả |

---

## ANYTIME — Dùng bất cứ lúc nào

### Quản lý dự án & tài liệu

| Lệnh | Tên | Mục đích |
|---|---|---|
| `/bmad-help` | BMAD Help | Hỏi BMAD nên làm gì tiếp theo, hoặc giải thích workflow |
| `/bmad-correct-course` | Điều chỉnh hướng đi | Xử lý khi có thay đổi lớn giữa chừng (đổi yêu cầu, sự cố sprint...) |
| `/bmad-document-project` | Tài liệu hóa dự án | Phân tích dự án hiện có và tạo tài liệu đầy đủ |
| `/bmad-generate-project-context` | Tạo Project Context | Scan dự án, tạo file `project-context.md` tóm lược ngắn gọn cho AI agent |
| `/bmad-sprint-status` | Xem trạng thái Sprint | Tóm tắt tiến độ, điểm rủi ro của sprint đang chạy |

### Quick Flow — Tác vụ nhanh (không cần full planning)

| Lệnh | Tên | Mục đích |
|---|---|---|
| `/bmad-quick-spec` | Quick Spec | Tạo tech spec nhanh cho thay đổi nhỏ, tính năng đơn giản |
| `/bmad-quick-dev` | Quick Dev | Triển khai nhanh từ quick spec — không qua full BMAD flow |
| `/bmad-quick-dev-new-preview` | Quick Dev (Preview) | Bản thống nhất thử nghiệm: clarify → plan → implement → review trong 1 workflow |

### Review & Chất lượng tài liệu

| Lệnh | Tên | Mục đích |
|---|---|---|
| `/bmad-review-adversarial-general` | Adversarial Review | Review phê phán tìm điểm yếu, lỗ hổng trong bất kỳ tài liệu nào |
| `/bmad-review-edge-case-hunter` | Edge Case Hunter | Tìm tất cả edge case chưa xử lý — bổ sung cho adversarial review |
| `/bmad-editorial-review-prose` | Review văn phong | Kiểm tra văn phong, ngôn từ, độ rõ ràng của văn bản |
| `/bmad-editorial-review-structure` | Review cấu trúc | Đề xuất cắt bỏ, tổ chức lại, đơn giản hóa cấu trúc tài liệu |
| `/bmad-validate-prd` | Validate PRD | Kiểm tra PRD theo tiêu chuẩn trước khi tiếp tục |

### Tiện ích tài liệu

| Lệnh | Tên | Mục đích |
|---|---|---|
| `/bmad-distillator` | Distillator | Nén tài liệu dài thành phiên bản tối ưu cho LLM đọc — không mất thông tin |
| `/bmad-shard-doc` | Shard Document | Cắt tài liệu lớn (>500 dòng) thành các file nhỏ theo section |
| `/bmad-index-docs` | Index Docs | Tạo file index.md cho một thư mục tài liệu |
| `/bmad-brainstorming` | Brainstorming | Brainstorm tự do — dùng bất cứ lúc nào cần ý tưởng |
| `/bmad-party-mode` | Party Mode | Họp nhóm nhiều agent cùng thảo luận một vấn đề |

---

## AGENT SKILLS — Load agent trước, rồi ra lệnh

> Các workflow này không có slash command riêng. Cần gọi skill để load agent, sau đó dùng code lệnh.

| Skill để load | Agent | Code | Tên | Mục đích |
|---|---|---|---|---|
| `/bmad-tech-writer` | 📚 Paige (Tech Writer) | WD | Write Document | Soạn tài liệu chi tiết theo best practice |
| `/bmad-tech-writer` | 📚 Paige | US | Update Standards | Cập nhật tiêu chuẩn tài liệu trong agent memory |
| `/bmad-tech-writer` | 📚 Paige | MG | Mermaid Generate | Tạo sơ đồ Mermaid (flowchart, sequence, ERD...) từ mô tả |
| `/bmad-tech-writer` | 📚 Paige | VD | Validate Document | Review tài liệu theo tiêu chuẩn, đề xuất cải thiện cụ thể |
| `/bmad-tech-writer` | 📚 Paige | EC | Explain Concept | Giải thích khái niệm phức tạp bằng ngôn ngữ dễ hiểu + ví dụ |

### Các agent độc lập

| Skill | Agent | Khi nào dùng |
|---|---|---|
| `/bmad-analyst` | 📊 Mary (Business Analyst) | Phân tích nghiệp vụ, nghiên cứu thị trường |
| `/bmad-pm` | 📋 John (Product Manager) | Quản lý sản phẩm, viết PRD, phân rã stories |
| `/bmad-architect` | 🏗️ Winston (Architect) | Thiết kế kỹ thuật, kiến trúc hệ thống |
| `/bmad-dev` | 💻 Amelia (Developer) | Triển khai code theo story |
| `/bmad-qa` | 🧪 Quinn (QA Engineer) | Kiểm thử, tạo test case |
| `/bmad-sm` | 🏃 Bob (Scrum Master) | Quản lý sprint, tạo story |
| `/bmad-tech-writer` | 📚 Paige (Tech Writer) | Viết và chuẩn hóa tài liệu |
| `/bmad-ux-designer` | 🎨 Sally (UX Designer) | Thiết kế UX/UI |
| `/bmad-quick-flow-solo-dev` | 🚀 Barry (Quick Flow) | Tác vụ nhanh, không cần full planning |
| `/bmad-advanced-elicitation` | — | Đẩy LLM suy nghĩ lại, tinh chỉnh output vừa tạo |
| `/bmad-product-brief-preview` | 📊 Mary | Tạo/cập nhật product brief qua discovery có hướng dẫn |

---

## Luồng làm việc chuẩn (BMM Full Flow)

```
[1-Analysis]  brainstorming → domain-research → create-product-brief
      ↓
[2-Planning]  create-prd* → validate-prd → create-ux-design
      ↓
[3-Solution]  create-architecture* → create-epics-and-stories* → check-implementation-readiness*
      ↓
[4-Implement] sprint-planning* → create-story* → dev-story* → code-review → (lặp lại)
```

> ⚠️ `*` = **Bắt buộc** phải hoàn thành trước khi tiếp tục

---

## Liên kết

- [[CLAUDE.md]] — Hướng dẫn làm việc với Nam & quy tắc dự án
- [[_bmad/bmm/config.yaml]] — Cấu hình BMAD module
