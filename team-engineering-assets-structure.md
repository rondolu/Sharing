# team-engineering-assets Repo Structure

## Repo 定位

這個 repo 是**開發者本機可 clone 的工程 reference repo**，主要供 VS Code 與 GitHub Copilot 在開發時直接使用。

這個 repo **不是**團隊一般文件倉庫，不承接申請流程、表單範本、會議紀錄、一般團隊資訊，這些內容由 **Microsoft Teams 公槽**負責。

## 設計原則

- 每一份放入 repo 的資產，都要能回答「開發者 clone 到地端後，在實作時會直接用到」。
- `.github` 是可載入規則層，`guides` 是人類理解層，`templates` 是專案起手層。
- 不建立 `common`、`shared`、`misc` 這類容易失控的黑洞資料夾。
- 凡是申請流程、填單範本、一般團隊資訊，改放 Microsoft Teams 公槽，不放 repo。

## 資產邊界分類表

| 層 | 放什麼 | 不放什麼 | 判斷標準 |
| --- | --- | --- | --- |
| `.github` | 給 VS Code / Copilot 原生載入的資產：agents、skills、prompts、共通 instructions | 每專案都不同的設定、單純人類閱讀說明 | 這份內容是否需要被工具直接載入與執行 |
| `guides` | 方法論、操作情境、開發 reference；多個 `.github` 資產需要一起理解時的搭配說明 | 單一資產的鏡像說明、申請流程、表單範本 | 這份內容是否主要是給人理解「何時用、怎麼搭配、為什麼這樣做」 |
| `templates` | 複製出去後再客製的起手資產：API checklist、service blueprints | 希望被原生載入的固定規則、純說明文件 | 這份內容是否預期每個新專案都要複製後修改 |

## 根目錄建議

```text
team-engineering-assets/
├── README.md
├── guides/
├── templates/
└── .github/
```

## 完整目錄樹

```text
team-engineering-assets/
├── README.md
│
├── guides/
│   ├── README.md
│   ├── asset-playbooks/
│   │   └── README.md  ← 只有多個 .github 資產需搭配說明時才在此新增
│   │
│   └── governance/
│       ├── README.md
│       ├── naming-conventions.md  ← 團隊 coding standard
│       └── asset-placement-rules.md  ← 檔案放置規則
│
├── templates/
│   ├── README.md
│   ├── service-requirements/
│   │   ├── README.md
│   │   └── api-service-requirements-checklist.md  ← AGENT 開發參考文件
│   │
│   └── service-blueprints/
│       ├── README.md
│       ├── fastapi-base/
│       │   ├── README.md
│       │   └── fast-api.py
│       │
│       ├── logger-base/
│       │   ├── README.md
│       │   └── logger.py
│       │
│       └── gcp-service-test-base/
│           ├── README.md
│           └── gcp-service-test.py
│
└── .github/
    ├── README.md
    ├── agents/
    │   └── README.md
    ├── prompts/
    │   └── README.md
    ├── skills/
    │   └── README.md
    ├── instructions/
    │   └── README.md
    └── workflow/
        └── README.md
```

## 既有共用項目落位（Refined）

| 項目 | 落點 | 說明 |
| --- | --- | --- |
| BQ 版控操作手冊 | `guides/bigquery/bq-version-control.md` | 從 PDF 重構為 Markdown，保留使用情境與對應 command line |
| API 服務需求 Checklist | `templates/service-requirements/api-service-requirements-checklist.md` | 給每個新 API 服務複製後客製的起手模板；不固化為共通 instructions |
| copilot-agent | `.github/agents/` | 原生載入 |
| copilot-skill | `.github/skills/` | 原生載入 |
| copilot-workflow / code-review | `.github/prompts/` | 資產本體在此；只有當多資產需搭配說明時才補 `guides/asset-playbooks/` |
| fastapi-base 框架 | `templates/service-blueprints/fastapi-base/` | 複製出去當起始骨架 |
| logger-base | `templates/service-blueprints/logger-base/` | 複製出去當起始骨架 |
| GCP_SERVICE_TEST 框架 | `templates/service-blueprints/gcp-service-test-base/` | 複製出去當起始骨架 |

## 各層用途邊界

### `.github/`（Load）

- 只放需要被 VS Code / GitHub Copilot 原生載入的資產：agents、skills、prompts、instructions。
- 共通 instructions 僅放跨專案穩定不變的規則；不放每個服務都需要客製的設定。
- 不要額外包一層 `ai-tools/` 或 `copilot/`，否則失去原生 discovery 效果。

### `guides/`（Understand）

- 只放開發者在實作時會直接查閱的方法論與操作情境 reference。
- `.github` 資產組合說明只有在多個資產需要一起理解、搭配使用時，才在此新增說明文件。
- 單一 Copilot 資產應自解釋（在資產本身 README 或前言），不要在 guides 建鏡像。
- 禁止放入：申請流程、表單範本、一般公告、會議紀錄、員工入職資訊。

### `templates/`（Copy）

- 放給開發者複製後依專案客製的起手資產。
- API 服務需求 checklist 屬於此層，因為每個新 API 服務的規格不同，應複製後調整，不固化為共通 instructions。
- 每個模板都應有 README，說明適用情境、使用步驟、限制。

## 治理規則

### 規則 1：新增資產放置決策流程

1. 是否需要被工具直接載入執行？→ `.github`
2. 是否主要讓人理解方法論、操作情境，且涉及多個 .github 資產搭配？→ `guides`
3. 是否是複製後再客製的起手資產？→ `templates`
4. 以上都不是，或屬於申請流程、表單、一般團隊資訊？→ **Teams 公槽，不放 repo**

### 規則 2：Copilot 資產與說明的配對原則

- 單一資產：自解釋，不另外建 guides 說明。
- 多資產搭配：才在 `guides/asset-playbooks/` 補一份說明，說明何時用哪個組合。
- 至少保留 `.github/README.md` 內的索引條目，避免資產孤立。

### 規則 3：Template 最小可用性

- 每個 blueprint 必須是開發者可直接 clone 後執行的最小骨架。
- 必須包含：README（適用情境、使用步驟、限制）、`.env.example`、`pyproject.toml`。
- 每 6 個月確認是否仍有 2+ 人主動使用；無人使用則在各 Blueprint README 標記 Deprecated。

### 規則 4：guides 禁區

以下內容禁止放入 `guides/`：申請流程、表單填寫模板、一般最佳實踐知識庫、業務流程說明、會議紀錄、組織資訊。

## README 分層架構

- **根目錄 README**：Repo 定位與分工說明、三層邊界導覽（連結各層 README）、資產放置決策流程、Copilot 資產放置規則。
- **各層 README**（guides / templates / .github）：說明該層放什麼、不放什麼。
- **各 Blueprint README**：適用情境、使用步驟、限制。

## 命名建議

- 目錄統一使用 kebab-case。
- 文件名稱以用途為主，不要用模糊名稱如 `misc.md`、`notes.md`、`common.md`。
- 模板名稱建議加上 `-base`、`-template` 後綴，降低誤解。
- AI 資產名稱應對齊實際用途，例如 `code-review.prompt.md`、`backend-python.skill.md`。

## 後續可再補的項目

- 根目錄 `README.md` 初版
- `guides/` 各子目錄 README 初版
- `.github/` 各子目錄 README 初版
- `templates/service-blueprints/` 三套 blueprint 的完整最小骨架（補齊其餘結構檔）

## 目前已建立的規劃文件

- `team-engineering-assets-structure.md`（本文件）
- `team-engineering-assets-structure.html`（視覺化提案頁）
- `team-engineering-assets-README-template.md`
