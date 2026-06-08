# team-engineering-assets

開發者本機可 clone 的工程 reference repo，集中管理可直接複製使用的 service blueprints、可被 VS Code / Copilot 原生載入的資產，以及開發實作時會直接查閱的指南。

## Repo 是什麼

- 開發者 clone 到本機後，在 VS Code 開發時直接使用的工程 reference。
- 提供可複製後客製的 service blueprints 與 checklist 模板。
- 提供 Copilot 可原生載入的 agents、skills、prompts、instructions。
- 提供少量與開發實作高度相關的操作指南。

## Repo 不是什麼

- **不是**團隊一般文件倉庫。
- **不**存放申請流程、表單範本、一般公告、會議紀錄、員工資訊。
- 以上內容請至 **Microsoft Teams 公槽**查閱。

## 你可以在這裡找到什麼

| 類型 | 路徑 | 用途 |
| --- | --- | --- |
| 資產組合說明 | `guides/asset-playbooks/` | 多個 `.github` 資產需要一起使用時的說明 |
| repo 治理規則 | `guides/governance/` | 命名規則、資產放置規則 |
| 服務需求模板 | `templates/service-requirements/` | 給開發者複製後客製的需求清單模板 |
| 服務 blueprint | `templates/service-blueprints/` | 給新專案當起始骨架 |
| Copilot 資產 | `.github/` | 提供 VS Code / Copilot 原生載入的資產 |

## 目錄導覽

```text
team-engineering-assets/
├── README.md
├── guides/       ← 方法論與操作情境 reference
├── templates/    ← 複製後客製的起手資產
└── .github/      ← Copilot / VS Code 原生載入資產
```

## 資產層邊界

| 層 | 定位 | 判斷方式 |
| --- | --- | --- |
| `.github` | 工具直接載入執行 | 需要被 VS Code / Copilot 原生讀取 |
| `guides` | 人類理解方法論與操作情境 | 開發者實作時會直接查閱；多資產搭配說明 |
| `templates` | 複製後客製的起手資產 | 每個新專案都要複製後修改 |

## 使用方式

### 1. 使用 Copilot 資產

將整個 repo clone 到本機或加入 VS Code 工作區，讓 VS Code 自動讀取 `.github/` 內的資產。

若有多個 `.github` 資產需要一起使用，請先閱讀 `guides/asset-playbooks/README.md`。

### 2. 查閱開發指南

到 `guides/` 查閱與開發實作直接相關的操作 reference。

若不確定在哪，先查各層 `README.md`。

### 3. 複製模板

到 `templates/` 選取適合的 checklist 或 service blueprint，複製到自己的專案後依情境調整。

## 資產新增規則

新增內容前，依序判斷：

1. 需要被工具直接載入執行？→ `.github/`
2. 讓人理解方法論或多資產搭配情境？→ `guides/`
3. 複製後依專案客製的起手資產？→ `templates/`
4. 以上都不符合，或屬於申請流程、表單、一般資訊？→ **Teams 公槽，不放 repo**

不要放入以下類型的模糊目錄：

- `common/`
- `shared/`
- `misc/`
- `temp/`

## 命名規則

- 目錄名稱統一使用 kebab-case。
- 文件名稱需能直接表達用途，例如 `bq-version-control.md`、`code-review-workflow.md`。
- Blueprint 名稱建議加上 `-base` 後綴，例如 `fastapi-base/`。
- 模板名稱建議加上 `-template` 後綴，降低誤用風險。
- Copilot 資產名稱應對齊實際用途，例如 `code-review.prompt.md`、`backend-python.skill.md`。

## Copilot 資產放置規則

- `.github/agents/`：自訂 agent
- `.github/skills/`：自訂 skill
- `.github/prompts/`：自訂 prompt / workflow 入口
- `.github/instructions/`：專案層級 instructions
- `.github/workflow/`：Copilot workflow 定義

不要將 Copilot 資產放在 `.github/` 以外的自訂目錄，例如 `ai-tools/` 或 `copilot/`，否則會失去原生載入效果。

## 建議維護習慣

- 每個一級資料夾都保留 `README.md`，說明放什麼與不放什麼。
- 每個 service blueprint 都要有自己的 `README.md`，寫清楚適用情境、使用方式與限制。
- `.github/` 內的資產若需多資產搭配使用，要在 `guides/asset-playbooks/` 補一份說明。

## 後續建議

- 補齊各子目錄的 `README.md` 初版
- 建立 service blueprints 的完整最小骨架（補齊其餘結構檔）
