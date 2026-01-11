# 術語表

Prompt Orchestration Governance (POG) 框架中使用術語的全面定義。

---

## 核心概念

### Prompt Orchestration Governance (POG)
一個將 prompts 作為一級軟體資產跨軟體開發生命週期進行管理的全面框架。POG 提供系統化流程來發現、標準化、驗證、版本化和部署 prompts，同時維持治理和品質控制。

### Prompt
一個結構化、版本化的工件，編碼模型驅動執行的意圖、約束和上下文。在 POG 中，prompts 被視為一級軟體資產，可跨專案和團隊發現、測試和重複使用。

### 一級軟體資產
接受與原始碼相同等級嚴謹性、管理和治理的軟體工件。這包括版本控制、測試、文件、審查流程和生命週期管理。

---

## Prompt 類型

### Interaction Prompt
在探索、聊天互動或實驗工作期間使用的臨時、非正式 prompt。這些 prompts 通常不受治理，僅存在於聊天歷史或個人筆記中。

**範例**：在 ChatGPT 或 Claude 中詢問的一次性問題，以解決即時問題。

**生命週期階段**：初始、未治理狀態。

### Discovered Prompt
已被識別為有價值且值得捕捉以供重複使用的 interaction prompt。當 prompt 展示有效性和超出其原始上下文的潛在價值時，就會發生發現。

**範例**：在回顧會議中識別出持續產生高品質回饋的程式碼審查 prompt。

**生命週期階段**：被提名晉升為受治理資產。

### Normalized Prompt
已轉換為結構化、參數化和泛化範本的 discovered prompt。標準化移除專案特定細節並添加清晰的參數。

**範例**：
```
之前："審查我們身份驗證服務的這個 Python 函數"
之後："審查以下 {{LANGUAGE}} 程式碼用於 {{PURPOSE}}：\n{{CODE}}"
```

**生命週期階段**：結構化但尚未驗證。

### Validated Prompt
已通過針對評估案例測試的 normalized prompt。驗證確保 prompt 在不同輸入中產生一致、高品質的結果。

**範例**：已針對 20 種不同函數類型驗證並持續產生全面測試套件的測試案例生成器。

**生命週期階段**：品質保證且可用於生產。

### Skill Prompt
經過驗證、可用於生產、版本化和受治理的 prompt 工件。Skill prompts 是 POG 生命週期的最終目標作為組織知識一部分管理的可重複使用資產。

**範例**："程式碼審查助手 v2.1" 儲存在 prompt repository 中，具有完整的元資料、版本控制和使用追蹤。

**生命週期階段**：可用於生產的受治理資產。

---

## POG 組件

### Prompt Warehouse Management
POG 的第一個核心功能。一個系統化流程來發現、標準化、驗證、版本化和儲存 prompts 作為可重複使用的資產。作為將 interaction prompts 轉換為 skill prompts 的「工廠」。

**關鍵活動**：
- 發現有價值的 prompts
- 標準化為範本
- 針對測試案例驗證
- 版本控制和儲存

### SDLC Integration
POG 的第二個核心功能。組織和部署階段特定的 prompts 以加速軟體開發生命週期的每個階段。

**關鍵活動**：
- 按 SDLC 階段組織 prompts
- 按需提供階段適當的 prompts
- 收集使用回饋
- 持續改進

### Prompt Repository
受治理 prompt 工件的集中式、版本化儲存。Repository 作為組織中所有 skill prompts 的單一事實來源。

**特徵**：
- 版本控制（通常基於 Git）
- 可搜尋和可發現
- 包含元資料（標籤、使用統計、評分）
- 具有治理的存取控制

### Meta-Loop
POG 框架本身的持續改進機制。Meta-loop 收集使用數據、回饋和指標，以系統化方式隨時間改進 prompt 函式庫。

**流程**：
1. 團隊使用 repository 中的 prompts
2. 收集使用指標和回饋
3. 評估效能
4. 推廣高價值 prompts
5. 棄用低價值 prompts
6. 識別並填補缺口

---

## 生命週期階段

### Discovery Phase（發現階段）
識別值得捕捉和正式化的有價值 interaction prompts 的流程。發現可以是主動的（挖掘聊天歷史）或被動的（開發者提交 prompts）。

**活動**：
- 挖掘聊天歷史和日誌
- 開發者提交
- 團隊回顧會議
- 使用模式分析

### Normalization Phase（標準化階段）
將 discovered prompts 轉換為可跨上下文重複使用的結構化、參數化範本。移除專案特定細節並添加清晰的參數。

**活動**：
- 提取核心意圖
- 識別參數
- 泛化約束
- 添加元資料
- 文件使用方法

### Validation Phase（驗證階段）
針對評估案例測試 prompts 以確保品質、一致性和有效性。驗證防止低品質 prompts 進入 repository。

**活動**：
- 定義測試案例
- 針對多個輸入執行
- 衡量品質指標
- 收集同儕審查
- 批准或拒絕

### Repository Management（Repository 管理）
持續維護 prompt repository，包括版本控制、組織、搜尋、存取控制和棄用。

**活動**：
- 版本控制
- 元資料管理
- 搜尋和發現
- 存取權限
- 使用追蹤
- 棄用過時的 prompts

---

## SDLC 階段

### Requirements Phase（需求階段）
軟體開發的初始階段，專注於理解和記錄需要建立的內容。

**POG Prompts**：使用者故事生成、驗收標準、利害關係人訪談指南、需求驗證。

### Design Phase（設計階段）
專注於規劃系統架構、介面和資料模型的階段。

**POG Prompts**：架構模式建議、API 設計、資料模型生成、設計審查。

### Development Phase（開發階段）
專注於編寫、審查和記錄程式碼的階段。

**POG Prompts**：程式碼生成、程式碼審查、文件生成、重構建議。

### Testing Phase（測試階段）
專注於驗證系統正確運作並滿足需求的階段。

**POG Prompts**：測試案例生成、測試資料創建、錯誤分析、覆蓋率分析。

### Deployment Phase（部署階段）
專注於將系統發佈到生產環境的階段。

**POG Prompts**：發佈說明生成、配置驗證、部署規劃、回滾程序。

### Maintenance Phase（維護階段）
專注於監控、除錯和改進生產中系統的持續階段。

**POG Prompts**：事件分析、效能優化、技術債務評估、文件更新。

---

## 編排概念

### Orchestration Layers（編排層級）
按範圍和抽象層級的 prompts 階層組織。層級從底部（foundation）到頂部（runtime context）組合。

**層級**（從底到頂）：
1. **Foundation Layer（基礎層）**：核心能力和約束
2. **Domain Layer（領域層）**：業務規則和領域知識
3. **Task Layer（任務層）**：特定意圖和動作
4. **Runtime Context Layer（執行時期上下文層）**：動態使用者輸入和環境

### Foundation Layer（基礎層）
包含核心系統能力、安全約束和組織政策的基礎層，適用於所有 prompts。

**範例**：速率限制、內容政策、安全約束、基礎模型能力。

### Domain Layer（領域層）
與特定領域或產業相關的業務特定規則、術語和模式。

**範例**：金融法規、醫療協議、電子商務模式、法律術語。

### Task Layer（任務層）
完成特定開發任務的特定意圖和動作。

**範例**："生成單元測試"、"審查 API 設計"、"創建使用者故事"、"分析安全漏洞"。

### Runtime Context Layer（執行時期上下文層）
在執行時注入的動態上下文，包括使用者輸入、專案狀態、環境變數和會話資訊。

**範例**：當前檔案內容、使用者角色、專案語言、git 分支、環境（dev/staging/prod）。

---

## 治理概念

### Control Plane（控制平面）
管理 prompt 生命週期的治理機制，包括版本控制、存取控制、稽核軌跡、品質關卡和合規性。

**組件**：
- 版本控制系統
- 存取控制（RBAC）
- 稽核記錄
- 品質關卡
- 合規檢查

### Version Control（版本控制）
系統化追蹤 prompts 隨時間的變更。每個版本都有唯一識別碼、變更日誌，並在可能的情況下維持向後相容性。

**方法**：
- 基於 Git（標籤、分支）
- 語義版本控制（v1.2.3）
- 基於時間戳
- 基於雜湊

### Access Control（存取控制）
基於角色的權限，決定誰可以創建、修改、批准或使用 prompts。

**常見角色**：
- **Contributor（貢獻者）**：可以提交 prompts
- **Reviewer（審查者）**：可以批准/拒絕 prompts
- **Maintainer（維護者）**：可以管理 repository
- **User（使用者）**：可以使用 prompts
- **Admin（管理員）**：完整管理存取權限

### Audit Trail（稽核軌跡）
prompt 使用的完整歷史，包括誰在何時出於何種目的使用了哪個 prompt 以及產生了什麼結果。

**追蹤資訊**：
- 使用者身份
- 時間戳
- Prompt 版本
- 輸入/輸出（已清理）
- 成功/失敗
- 回饋

### Quality Gate（品質關卡）
prompt 生命週期中需要驗證才能進展的檢查點。品質關卡確保只有經過測試、批准的 prompts 達到生產環境。

**類型**：
- 語法驗證
- 評估測試通過
- 同儕審查批准
- 安全掃描
- 合規檢查

---

## 評估與測試

### Evaluation Case（評估案例）
prompt 的測試案例，由輸入場景和預期輸出特徵組成。用於驗證 prompt 品質和一致性。

**組件**：
- 輸入範例
- 預期輸出模式
- 品質標準
- 通過/失敗閾值

**範例**：
```
輸入："審查這段程式碼：function add(a,b) { return a+b }"
預期：包含「沒有錯誤處理」、「缺少類型提示」
品質：識別至少 2 個程式碼品質問題
```

### Regression Test（回歸測試）
確保 prompt 在修改後繼續良好運作的測試。防止 prompt 演進過程中的品質退化。

### A/B Test（A/B 測試）
兩個 prompt 變體的對照比較，以確定哪個效能更好。用於 prompt 優化。

**指標**：成功率、品質分數、使用者偏好、延遲、成本。

### Usage Metrics（使用指標）
關於 prompt 使用模式的量化數據，包括頻率、成功率、使用者評分和效能指標。

**收集的數據**：
- 使用次數
- 唯一使用者
- 成功/失敗率
- 平均延遲
- 每次執行成本
- 使用者滿意度分數

---

## 實施方法

### GitOps-Based（基於 GitOps）
一種實施方法，其中 prompts 作為程式碼儲存在 Git repositories 中，使用基於 PR 的審查工作流程。

**特徵**：
- Prompts 作為 markdown/YAML 檔案
- Git 用於版本控制
- Pull requests 用於審查
- CI/CD 用於驗證
- 基於分支的工作流程

### Platform-Based（基於平台）
使用專用 prompt 管理平台與 UI 驅動工作流程的實施方法。

**特徵**：
- 基於 Web 的介面
- 資料庫支援的儲存
- 內建搜尋和分析
- 基於角色的存取控制
- 用於程式化存取的 API

### API-Driven（API 驅動）
公開 RESTful API 用於程式化 prompt 存取和管理的實施方法。

**特徵**：
- REST/GraphQL API
- 程式化存取
- 整合友善
- 自動化支援
- 無頭架構

### Hybrid（混合式）
根據組織需求使用多種實施策略的方法組合。

**範例**：Git 用於版本控制 + 資料庫用於元資料 + API 用於執行時期存取。

---

## 相關方法論

### PDD (Prompt-Driven Development)
一種開發方法論，其中 prompts 是開發過程的主要驅動力。專注於個別開發者工作流程和快速迭代。

**與 POG 的關係**：互補。PDD 用於開發實踐，POG 用於治理。

查看：[POG vs PDD](comparisons/pdd.md)

### PDE (Prompt-Driven Engineering)
一種工程方法論，將 prompts 視為需要嚴謹設計、測試和維護的一級工程工件。

**與 POG 的關係**：互補。PDE 用於工程品質，POG 用於組織管理。

查看：[POG vs PDE](comparisons/pde.md)

### PromptOps
在生產環境中管理 prompt 部署、監控和維護的運維實踐。

**與 POG 的關係**：POG 提供治理框架；PromptOps 提供運維實踐。

### LLMOps
應用於大型語言模型生命週期的 MLOps 實踐，包括模型部署、監控和管理。

**與 POG 的關係**：POG 專注於 prompts；LLMOps 專注於模型。兩者都是 AI 運維的互補部分。

---

## 技術術語

### Parameterization（參數化）
識別並將 prompt 的可變部分提取為可在執行時期填充的命名參數的流程。

**範例**：
```
之前："為 authenticate 函數編寫 Python 測試"
之後："為 {{FUNCTION_NAME}} 函數編寫 {{LANGUAGE}} 測試"
```

### Context Injection（上下文注入）
在執行時期根據當前專案狀態、使用者會話或環境自動將相關資訊插入 prompt 的流程。

**範例**：
- 當前檔案內容
- Git 分支名稱
- 專案相依性
- 使用者偏好
- 環境變數

### Template（範本）
可重複使用的 prompt 結構，具有可填充特定值的參數。範本實現跨不同上下文的 prompt 重複使用。

**格式範例**：
- Jinja2：`{{ variable }}`
- Handlebars：`{{variable}}`
- Mustache：`{{variable}}`
- 自訂：`$VARIABLE` 或 `{variable}`

### Metadata（元資料）
關於 prompt 的結構化資訊，包括標籤、作者、版本、使用統計、評分和關係。

**常見欄位**：
- 名稱和描述
- 版本和作者
- 創建/修改日期
- SDLC 階段
- 標籤和類別
- 使用統計
- 品質評分
- 相關 prompts

### Semantic Search（語義搜尋）
理解含義和意圖而不僅僅是匹配關鍵字的搜尋能力。使即使使用不同措辭也能找到相關 prompts。

**技術**：向量嵌入、相似性搜尋、語義索引。

---

## 指標與衡量

### Adoption Rate（採用率）
積極使用 POG repository 中 prompts 的開發者或團隊百分比。

**計算**：(活躍使用者 / 總使用者) × 100

### Reuse Rate（重複使用率）
重複使用 prompts 而非從頭創建的頻率。

**計算**：(重複使用的 prompts / 總 prompt 使用量) × 100

### Time-to-Value（價值實現時間）
從 prompt 發現到在 repository 中生產部署的持續時間。

**目標**：在維持品質的同時最小化。

### Coverage（覆蓋率）
有可用 prompts 的 SDLC 階段或開發任務的百分比。

**計算**：(有 prompts 的階段 / 總階段) × 100

### Quality Score（品質分數）
基於驗證測試、使用者評分和成功指標的 prompt 有效性的聚合衡量。

**組件**：測試通過率、使用者滿意度、成功率、同儕審查。

### ROI (Return on Investment)
與成本相比，從 POG 實施獲得的財務收益。

**計算**：(節省的時間 × 時薪 - 運營成本) / 運營成本 × 100

---

## 組織術語

### Prompt Champion（Prompt 倡導者）
熱心的倡導者，在團隊或部門內推廣 POG 採用、提供培訓和支援使用者。

**職責**：宣傳、培訓、支援、回饋收集。

### Prompt Maintainer（Prompt 維護者）
負責管理 prompt repository、審查提交和確保品質標準的人員或團隊。

**職責**：Repository 管理、審查/批准、品質保證、棄用決策。

### Contributor（貢獻者）
創建並提交 prompts 到 repository 的任何團隊成員。

**職責**：創建高品質 prompts、提供文件、回應回饋。

### Governance Team（治理團隊）
負責建立 prompt 管理的政策、標準和合規要求的團體。

**職責**：政策制定、合規監控、稽核審查、風險管理。

---

## 變革管理

### Pilot Team（試點團隊）
在組織全面推出之前選擇測試 POG 實施的小組。提供回饋並識別問題。

**選擇標準**：熱心、代表更廣泛的組織、願意提供回饋。

### Champions Network（倡導者網絡）
跨不同團隊的分散式 prompt 倡導者團體，推廣採用並提供同儕支援。

### Quick Win（快速成效）
展示 POG 價值並為更廣泛採用建立動力的早期可見成功。

**範例**：常見任務節省 50% 時間、更快的入職、改進的程式碼品質。

---

*完整框架文件，請參閱[主要 POG 文件](index.md)。*
