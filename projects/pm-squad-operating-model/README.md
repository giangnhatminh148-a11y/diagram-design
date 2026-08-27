# PM Squad — Operating Model Diagrams (v0.1, draft)

Two diagrams requested at the end of the Notion page **"PM Squad — Socratic Drill & Operating Model"** (§ Kết luận), built from its full-context sections (2, 3, 5–9).

- [`01-org-operating-model.html`](./01-org-operating-model.html) — Target Organization & Operating Model: reporting lines, PM Squad, internal specialist pools, cross-functional interfaces, Phó phòng / Trưởng phòng.
- [`02-project-lifecycle.html`](./02-project-lifecycle.html) — End-to-End Project Lifecycle: PM involvement across stages, BOD gate, Contract Signed → Delivery activation.

Open directly in a browser — self-contained HTML/SVG, no build step.

## Status

**Draft v0.1 — chờ Minh xác nhận**, đúng tinh thần Notion gốc: "dựng diagram thô, sau đó dùng sơ đồ đó làm vật thể để tiếp tục Socratic Drill." Không phải sơ đồ tổ chức chính thức.

## Cần Minh xác nhận trước khi merge

1. **Quyền PM "Kích hoạt Delivery Stage sau Contract Signed"** — câu 2.1 trong Notion ghi "Cái này là gì tôi chưa hiểu". Diagram 2 hiện vẽ Contract Signed (PKD) như một **trigger sự kiện** vào Reconciliation (PM), không phải một quyền PM chủ động kích hoạt — cách hiểu này khớp với mục 5 ("Full context chốt để dựng diagram") nhưng **chưa được bạn xác nhận trực tiếp**.
2. **"Escalate khi deadline/quality gate bị vi phạm"** (câu 2.1, ghi "làm sau") — cố ý **không vẽ** như quyền PM chính thức trong Diagram 1/2.
3. **Simplification cho v0.1** (Diagram 2): gộp "PM + Mentor" thành overlay dashed thay vì lane riêng; gộp Document Control/Admin + Strategic & System Design vào diagram 1 only (không lặp lại ở lifecycle) để giữ mật độ ≤9 node/step — nếu cần tách riêng, báo lại.
4. **Theme màu**: dùng brand ThuanHai (mapped từ `thuanhaipricingtool` Tailwind tokens, primary blue `#1669b1`) — xem `skills/diagram-design/references/style-guide.md` mục "Custom tokens — ThuanHai Energy".

## Chưa vẽ như quyết định cuối (theo đúng mục 10 của Notion)

Salary bands / P1–P2–P3 / phụ cấp; số lượng PM thực tế + capacity limit; tên cụ thể mentor lò hơi/xây dựng; RACI chi tiết PM vs Mentor vs Sale vs specialist; resource-allocation formula; trigger/template liên phòng chi tiết; SOP sau Contract Signed; checklist survey/BOD/contract reconciliation; KPI.

## Nguồn

- Notion: **PM Squad — Socratic Drill & Operating Model** (`3c921b02-b17e-818f-a6de-d83809af0181`)
- `thuanhaipricingtool` repo: `docs/PM_SQUAD_OPERATING_MODEL_V1.md`, `docs/SOP_PTDA_V1.md`
