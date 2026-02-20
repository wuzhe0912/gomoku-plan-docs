# plan-docs 退場與遷移清單

最後更新：2026-02-20
適用範圍：`gomoku-plan-docs` 是否可封存/刪除的決策與執行步驟。

## 放置位置評估

- 建議放在：`gomoku-plan-docs/` 根目錄
- 原因：
  - 這份清單是 `plan-docs` 自身的退場規則，應該跟著來源 repo 管理。
  - 刪除前，能在同 repo 一次看到「現況、搬遷目標、刪除 gate」。
  - 後續若要封存，只要保留這份檔案即可快速回溯決策。

## 目前需遷移資產（盤點）

- `CLAUDE.md`：產品規劃、Phase 拆解、週任務、技術選型。
- `ENGINEERING-CONVENTIONS.md`：跨 repo commit/branch/安全規範。

## 遷移目標建議

- `CLAUDE.md` 的內容拆分：
  - Client 相關：搬到 `gomoku-client/docs/roadmap/`（例如 `v0.0.1-client-roadmap.md`）
  - Server 相關：搬到 `gomoku-server/docs/roadmap/`（例如 `v0.0.1-server-roadmap.md`）
  - 共用里程碑：各 repo README 摘要 + 連到各自 roadmap
- `ENGINEERING-CONVENTIONS.md` 的內容：
  - 以各 repo `CLAUDE.md` 為主來源（目前已部分同步）
  - 若要保留獨立版，應分別放在：
    - `gomoku-client/docs/conventions/engineering.md`
    - `gomoku-server/docs/conventions/engineering.md`

## 執行清單（逐步勾選）

### A. 搬遷前檢查

- [ ] A-001 `gomoku-client` README 已包含 roadmap 入口
- [ ] A-002 `gomoku-server` README 已包含 roadmap 入口
- [ ] A-003 `gomoku-client`/`gomoku-server` 都有可執行的本地啟動說明
- [ ] A-004 兩個 repo 的 `CLAUDE.md` 都已含 commit/branch/安全規範

### B. 文件遷移

- [ ] B-001 新建 `gomoku-client/docs/roadmap/` 並放入 client 路線圖
- [ ] B-002 新建 `gomoku-server/docs/roadmap/` 並放入 server 路線圖
- [ ] B-003 將 `CLAUDE.md` 的內容拆分並搬遷完成
- [ ] B-004 將共用規範同步到 client/server（避免只留在 plan-docs）
- [ ] B-005 更新所有跨 repo 連結（README、文件內部連結）

### C. 封存判定 Gate（滿足才可封存）

- [ ] C-001 連續 2 週內，沒有新 commit 需要回寫到 `gomoku-plan-docs`
- [ ] C-002 任一新成員只靠 client/server 文件即可啟動開發（無需看 plan-docs）
- [ ] C-003 `plan-docs` 中所有文件在其他 repo 都有對應版本

### D. 刪除判定 Gate（滿足才可刪除）

- [ ] D-001 已先執行封存（Archive）至少 2-4 週
- [ ] D-002 期間內無人反饋需查 `plan-docs` 歷史文件
- [ ] D-003 所有外部連結已改指向 client/server 文件
- [ ] D-004 已建立最後備份標記（tag 或 release note）

## 決策建議

- 現階段（2026-02-20）：先不要刪除，先進入「遷移 + 封存準備」。
- 建議節奏：
  1. 先完成 A + B
  2. 觀察 2 週進入 C
  3. 再決定是否進 D（刪除）
