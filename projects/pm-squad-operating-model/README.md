# PM Squad — Operating Model Diagrams (v0.1, draft)

Built from the Notion page **"PM Squad — Socratic Drill & Operating Model"** (§ Kết luận + follow-up feedback 27–28/08). There are **2 independent, mutually-exclusive org-structure options** to compare, plus **2 workflow diagrams** (Development Stage, Execution Stage) that hold regardless of which org option is chosen.

## Org structure — pick one (không kết hợp)

- [`branch-1-project-development-execution-subdept/project-development-execution-org-model.html`](./branch-1-project-development-execution-subdept/project-development-execution-org-model.html) — **Option A**, tổ chức theo **giai đoạn dự án**: 2 sub-department độc lập, mỗi bên **1 trưởng bộ phận riêng** — Trưởng BP Phát Triển Dự Án và Trưởng BP Triển Khai Dự Án. Dự án đổi chủ quản lý khi Contract Signed.
- [`branch-2-pm-squad-expertise-pool/pm-squad-expertise-pool-org-model.html`](./branch-2-pm-squad-expertise-pool/pm-squad-expertise-pool-org-model.html) — **Option B**, tổ chức theo **vai trò**: PM Squad (có Trưởng PM Squad làm team lead, PM giữ xuyên suốt dự án) và Expertise (flat, không có team lead riêng, làm việc dưới chỉ dẫn Phó phòng).

Cả 2 phương án đều giữ **Phó Phòng Dự Án** ở cùng vị trí/vai trò — chỉ khác ở tầng ngay bên dưới. Lựa chọn này ảnh hưởng trực tiếp tới KPI, RACI và scope thảo luận sau này — **chưa chốt**.

## Workflow — dùng chung cho cả 2 option

- [`workflow-project-lifecycle/project-lifecycle.html`](./workflow-project-lifecycle/project-lifecycle.html) — **Project Development Stage**: Intake → Assign → Survey → Assess → Scenario → **BOD Gate** → PKD đàm phán (hỗ trợ kỹ thuật) → Contract Signed → tính lại hiệu quả đầu tư sau ký → bàn giao sang Project Execution Stage.
- [`workflow-project-lifecycle/project-execution-stage.html`](./workflow-project-lifecycle/project-execution-stage.html) — **Project Execution Stage** (mới, 28/08) — dựng từ dữ liệu thật, không phải suy đoán: 4 pillar **Xây Dựng → Mua Hàng &amp; Chế Tạo → Lắp Đặt → Nghiệm Thu**, lấy từ `wbs_catalog` + adoption thật trong `progress_items`/`tasks` (query trực tiếp Lovable project `pdathuanhai`).

## Phát hiện quan trọng (28/08) — điều chỉnh lại giả định trước đó

Trước đó tài liệu này ghi "SOP giai đoạn Triển khai chưa được nạp". Sau khi query trực tiếp `ProgressBoard.tsx`/`TaskBoard.tsx` + DB thật:

- **SOP Execution Stage đã tồn tại** — bảng `wbs_catalog` (scope `applies_to='steam'`, 45 dòng) chuẩn hoá đúng 4 pillar trên, mỗi hạng mục có adoption thật 1–10 dự án (verify qua `progress_items` JOIN `wbs_catalog` + `tasks` GROUP BY title).
- Phát hiện thêm 1 lớp **work-package thiết bị** (130 dòng trong `tasks.task_type='work_package'`: Bồn dầu, Multicyclone, Hệ tải xỉ, Lọc bụi túi, PLC-SCADA, Bộ sấy không khí, Quạt cấp/hút, Hệ cấp liệu, Bộ hâm nước, Bộ sinh hơi...) — breakdown per-thiết bị dùng thật trong Mua Hàng/Lắp Đặt nhưng **chưa được chuẩn hoá vào `wbs_catalog`** (hiện chỉ là task tự do, không tự seed cho dự án mới).
- **Giới hạn**: `wbs_catalog` chỉ có scope `steam` (Lò Hơi). Dự án Xây Dựng thuần hoặc Biomass **chưa có catalog tương đương** — "Team Triển Khai" ở Option A vẫn ghi rõ đây là giới hạn chưa xử lý.

## Status

**Draft v0.1 — chờ Minh xác nhận.** Không phải sơ đồ tổ chức chính thức; dùng làm vật thể để tiếp tục Socratic Drill.

## Cần Minh xác nhận trước khi chốt

1. Chọn Option A hay Option B (hoặc yêu cầu phương án thứ 3).
2. Có muốn chuẩn hoá lớp work-package thiết bị (130 dòng) vào `wbs_catalog` level-4 để tự seed cho dự án mới không, hay giữ nguyên cơ chế tự do như hiện tại?
3. Có cần catalog riêng cho scope Xây Dựng/Biomass (tương tự `wbs_catalog` cho steam) không?
4. Quyền PM "Kích hoạt Delivery Stage sau Contract Signed" và "Escalate khi deadline/quality gate bị vi phạm" — vẫn **chưa vẽ** như quyền chính thức ở bất kỳ diagram nào.

## Chưa vẽ / chưa nạp

- Lane Pháp Lý riêng trong Execution Stage (PCCC/môi trường/nghiệm thu pháp lý chạy song song — có chú thích trên diagram, chưa vẽ đầy đủ).
- RACI chi tiết PM vs Nhà thầu vs NCC vs Đội lắp đặt; KPI/SLA từng mốc; checklist nghiệm thu đầy đủ; salary bands/P1-P2-P3; resource-allocation formula.

## Nguồn

- Notion: **PM Squad — Socratic Drill & Operating Model** (`3c921b02-b17e-818f-a6de-d83809af0181`)
- `thuanhaipricingtool` repo: `docs/PM_SQUAD_OPERATING_MODEL_V1.md`, `docs/SOP_PTDA_V1.md`, `src/components/ProgressBoard.tsx`, `src/components/TaskBoard.tsx`
- Lovable project `pdathuanhai` (Thuan Hai Energy - Phòng Dự Án, id `c9dd60d5-eec2-4df1-bbe0-9326f062b428`) — `wbs_catalog`, `progress_items`, `tasks`, query 28/08/2026.
